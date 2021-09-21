'''sh
start-stop-server-in-background.sh
# starting simple HTTP server with Python in background
screen -d -m python -m SimpleHTTPServer 7777

# killing process running with screen in background
kill -9 `top -n 1 | pgrep screen`
