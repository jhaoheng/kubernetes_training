# 安裝 kubernetes client 
> [官網安裝](https://kubernetes.io/docs/imported/release/notes/)

1. 進入安裝頁面
2. 選擇 client binaries
3. 確定自己電腦的 linux 安裝即可 : osx amd64 
	- `uname -a` : 看是否是 x86_64
	- `shasum -a 256 {the file} | grep {hash}` : 在 osx 驗證 hash
4. 放入 bash_profile, `source ~/.bash_profile` 即可