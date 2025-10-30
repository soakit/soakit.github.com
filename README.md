# blog

## Windows环境运行步骤

1. 安装Ruby和DevKit（从 https://rubyinstaller.org/downloads/ 下载）

2. 安装bundler
```bash
gem install bundler
```

3. 安装依赖
```
bundle install
```
4. 运行服务
```
bundle exec jekyll serve
```

## Mac环境运行步骤

1. `sudo gem install bundler`

2. `sudo bundle install`

3. `jekyll serve`

## 出错
### 下载速度慢

可以先切换到Ruby China的源：
```shell
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
```

### 清理并重新安装依赖
```shell
rm Gemfile.lock
bundle install
```
