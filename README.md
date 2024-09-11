# Science of science研究会 2024 オフィシャルウェブサイト

本リポジトリは、Science of science研究会の公式ウェブサイト用リポジトリです。
本コードは、[ACL 2023](https://github.com/acl-org/acl-2023)からフォークしておりますので、編集の詳細につきましてはフォーク元のREADMEをご覧ください。

- Webpage: https://sciscijp.github.io/scisciconfJP2024_A/

## How to contribute

### 1. Clone

```
git clone git@github.com:ScisciJP/scisciconfJP2024.git
```

### 2. Build with Jekyll
Install bundler:
```
sudo gem install bundler.
```

Make sure you have Ruby and Bundler versions > 2.4.

Clone this repository. Note that this repository uses submodules so to properly check out the submodule code, run `git submodule init` and `git submodule update` after you clone the repository. You will need the submodule to generate the schedule for the website.

Run the gems needed by this repository: 
```
sudo bundle install.
```
Note: This step might fail when installing the `nokogiri` gem. If this happens, run `bundle config build.nokogiri --use-system-libraries` and then `run bundle install` again.


Start the jekyll server by running 
```
bundle exec jekyll serve
```

### 2. Build with docker


```
cd scisciconfJP2024
docker build -t scisciconfjp2024/website .
docker run --rm -p 4000:4000 -v $(pwd):/srv/jekyll scisciconfjp2024/website
```

-> http://0.0.0.0:4000/scisciconfJP2024/ からアクセスできます。

if you fail with the following "failed to authorize" error, remember you should login to docker first.
```
--------------------
   1 | >>> FROM jekyll/jekyll
   2 |     
   3 |     COPY ./Gemfile *.gemspec ./
--------------------
ERROR: failed to solve: jekyll/jekyll: failed to resolve source metadata for docker.io/jekyll/jekyll:latest: failed to authorize: failed to fetch oauth token: unexpected status from GET request to https://auth.docker.io/token?scope=repository%3Ajekyll%2Fjekyll%3Apull&service=registry.docker.io: 401 Unauthorized
Unable to find image 'scisciconfjp2024/website:latest' locally
```

you would want to run:
```
docker login
```

### 3. Edit pages

branchを切ってから、編集してください。
編集する回数の多い箇所は、フォーク元の[こちら](https://github.com/acl-org/acl-2023?tab=readme-ov-file#important-files)に記載があります。

### 4. Push to repository

```
git commit -m "編集内容"
git push origin <branch_name>
```

- push後は、プルリクエストを出してください。
- プログラム委員が確認次第、随時更新します。


# プログラム運営委員

Contact: [sciscijp@googlegroups.com](mailto:sciscijp@googlegroups.com)

* 三浦 崇寛(東京大学)
* 三浦 千哲(東京大学)