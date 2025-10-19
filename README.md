1. Clone the markdown file repo.
    ```bash
    git clone git@github.com:kkraman02/docs_kkraman02_github.git
    ```
2. Do the changes/add files in the `/source` of docs_kkraman02_github directory and compile the MD to HTML
    ```bash
    hexo clean
    hexo g
    hexo s  //(optional)
    ```
3. Update the contents to remote from local
    ```bash
    cd docs_kkraman02_github
    git add .
    git commit -am "commit message"
    git push
    ```
4. Copy & paste the `/public` directory files to this repo.
    ```bash
    cp -rfv /docs_kkraman02_github/public/* kkraman02.github.io
    ```
5. Update the contents to remote from local
    ```bash
    cd kkraman02.github.io
    git add .
    git commit -am "commit message"
    git push
    ```
