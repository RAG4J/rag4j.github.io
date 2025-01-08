# rag4j.github.io

## Running the site locally
[Original documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)

```bash
bundle exec jekyll serve
```


Install steps

```bash
brew install chruby ruby-install
ruby-install ruby 3.3.5


echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.3.5" >> ~/.zshrc # run 'chruby' to see actual version

ruby -v

# Toevoegen aan ~/.zshrc
export GEM_HOME=$HOME/.gem
export PATH=$HOME/.gem/bin:$PATH

source ~/.zshrc

gem install jekyll --user-install
```


