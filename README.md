My Brewfile managed by [homebrew-file](https://github.com/rcmdnk/homebrew-file).

Once my Mac is replaced or recovered, run:

```
$ curl -fsSL https://raw.github.com/rcmdnk/homebrew-file/install/install.sh |sh
```

Add the following code to my .bashrc:

```
if [ -f $(brew --prefix)/etc/brew-wrap ];then
  source $(brew --prefix)/etc/brew-wrap
fi
```
