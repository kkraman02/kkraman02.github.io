Clone the markdown file repo.
```bash
git clone git@github.com:kkraman02/docs_kkraman02_github.git
```
Do the changes/add files in the `/source` of docs_kkraman02_github directory and compile the MD to HTML
```bash
hexo clean
hexo g
hexo s  //(optional)
```
Update the contents to remote from local
```bash
cd docs_kkraman02_github
git add .
git commit -am "commit message"
git push
```
Copy & paste the `/public` directory files to this repo.
```bash
cp -rfv /docs_kkraman02_github/public/* kkraman02.github.io
```
Update the contents to remote from local
```bash
cd kkraman02.github.io
git add .
git commit -am "commit message"
git push
```
