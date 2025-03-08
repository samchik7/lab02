export GITHUB_USERNAME=samchik7
export GITHUB_EMAIL=s4gabalyan@yandex.ru
export GITHUB_TOKEN=token
alias edit=nano



cd ${GITHUB_USERNAME}/workspace
workspace % source scripts/activate



mkdir ~/.config
mkdir: /Users/sam/.config: File exists



mkdir ~/.config
mkdir: /Users/sam/.config: File exists
cat > ~/.config/hub <<EOF
heredoc> github.com:
heredoc> - user: ${GITHUB_USERNAME}
heredoc> oauth_token: ${GITHUB_TOKEN}
heredoc> protocol: https             
heredoc> EOF
git config --global hub.protocol https



mkdir projects/lab02 && cd projects/lab02
git init
Initialized empty Git repository in /Users/sam/samchik7/workspace/projects/lab02/.git/
git config --global user.name ${GITHUB_USERNAME}
git config --global user.email ${GITHUB_EMAIL}
git config -e --global
git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git
git pull origin master
fatal: couldn't find remote ref master
git status
On branch main
nothing to commit, working tree clean
git push origin master




git pull origin master
From https://github.com/samchik7/lab02
 * branch            master     -> FETCH_HEAD
Already up to date.
git log
commit d04040705bc8d6f6b1acb578805d477339c3923a (HEAD -> master, origin/master, main)
Author: samchik7 <s4gabalyan@yandex.ru>
Date:   Fri Mar 7 16:32:43 2025 +0300

    added  README.md

commit 1d85be9b0a5bf0e0aaf3204adf70a2b2b60a5eb0 (origin/main)
Author: samchik7 <s4gabalyan@yandex.ru>
Date:   Fri Mar 7 15:56:02 2025 +0300

    .gitignore

commit 2fc98922145c8ce194222a7ef823179427c3617a
Author: samchik7 <s4gabalyan@yandex.ru>
Date:   Wed Mar 5 22:24:37 2025 +0300

    Initial commit


mkdir sources
mkdir include
mkdir examples
cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
EOF




cat > include/print.hpp <<EOF
#include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
EOF



cat > examples/example1.cpp <<EOF
#include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
EOF




cat > examples/example2.cpp <<EOF
#include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF




git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store
	examples/
	include/
	sources/

nothing added to commit but untracked files present (use "git add" to track)
sam@h124 lab02 % git add .
sam@h124 lab02 % git add .
sam@h124 lab02 % git commit -m"added sources"
[master c5fabe7] added sources
 6 files changed, 32 insertions(+)
 create mode 100644 .DS_Store
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/.DS_Store
 create mode 100644 sources/print.cpp
git push origin master
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (11/11), 1.64 KiB | 1.64 MiB/s, done.
Total 11 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/samchik7/lab02.git
   d040407..c5fabe7  master -> master






 
