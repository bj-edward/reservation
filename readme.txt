https://github.com/tyrchen/simple-dns.git

cd ~/Development/Rust/tyrchen
git clone https://github.com/tyrchen/simple-dns.git

cd ~/Development/Rust/learning4tyrchen
mkdir reservation
cd reservation
➜  reservation touch Cargo.toml
➜  reservation touch README.md
➜  reservation cp -r ../../tyrchen/simple-dns/deny.toml .
➜  reservation cp -r ../../tyrchen/simple-dns/.github .
➜  reservation cp -r ../../tyrchen/simple-dns/.pre-commit-config.yaml .
➜  reservation cp -r ../../tyrchen/simple-dns/_typos.toml .

➜  reservation git init
➜  ~ sudo emerge dev-vcs/pre-commit
➜  reservation git:(master) ✗ pre-commit install
pre-commit installed at .git/hooks/pre-commit
➜  reservation git:(master) ✗ git status
➜  reservation git:(master) ✗ cargo new abi --lib
➜  reservation git:(master) ✗ cargo new reservation --lib
➜  reservation git:(master) ✗ cargo new service

➜  reservation git:(master) ✗ cargo build
➜  reservation git:(master) ✗ git status
➜  reservation git:(master) ✗ git add .
➜  reservation git:(master) ✗ git status

➜  reservation git:(master) ✗ git commit -a
init commit
:close
:wq

Create repositories:
https://github.com/bj-edward

➜  reservation git:(master) ✗ git remote add origin git@github.com/bj-edward/reservation.git
➜  reservation git:(master) ✗ git branch -M main
➜  reservation git:(main) ✗ git push -u origin main
error: src refspec main does not match any
error: failed to push some refs to 'git@github.com/bj-edward/reservation.git'

➜  reservation git:(main) ✗ git remote add origin git@github.com:bj-edward/reservation.git
error: remote origin already exists.
➜  reservation git:(main) ✗ git branch -M master
➜  reservation git:(master) ✗ git push -u origin master
error: src refspec master does not match any
error: failed to push some refs to 'git@github.com/bj-edward/reservation.git'

➜  reservation git:(master) ✗ git remote -v
origin	git@github.com:/bj-edward/reservation.git/ (fetch)
origin	git@github.com:/bj-edward/reservation.git/ (push)

➜  reservation git:(master) ✗ git commit -m "first commit"
➜  reservation git:(master) ✗ git remote set-url origin github.com:/bj-edward/reservation.git

➜  reservation git:(master) ✗ git push -u origin master -f
error: src refspec master does not match any
error: failed to push some refs to 'github.com:/bj-edward/reservation.git'

➜  reservation git:(master) ✗ git branch -a
With the above results, you can see that there is no master repository (origin/master). So when you try to push to that repository, you will get the "respec error".

➜  reservation git:(master) ✗ git checkout -b master
➜  reservation git:(master) ✗ cargo install --locked cargo-deny && cargo deny init && cargo deny check
