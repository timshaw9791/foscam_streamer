# Foscam Streamer

A small tool to stream your Foscam IP camera on the web, plugin-free.

## Testing

- Set the `FOSCAM_STREAM_URL` environment variable (e.g. `rtsp://user:pass@abcde.myfoscam.org:88/video`).
   可以查看代码发现就是设置process.env.FOSCAM_STREAM_URL
- Start the server with `node index.js`.
- Open the `test_client.html`. 用浏览器以本地html方式打开该文件都行

注意，
- 可以先不管watchdog和supervisor.如果要调整显示窗口的canvas的大小，可以看看原项目里的issue :-) 如何检索信息一个练习
- 再运行前当然要npm install,但这部完成后可以直接把node_modules中的node-rtsp-stream目录删掉，因为他主要是用自己的哪份，作者在下述中提到过。

## Watchdog

The watchdog will keep tailing the server log and restart the service if the log stops increasing in size (i.e. the camera is down).

- `python watchdog.py`

## Supervisor

It includes some supervisor configurations to run the server and the watchdog.

**IMPORTANT**: Make sure the absolute paths match your setup.

## Todo

- Absolute paths should be environment variables.
- Ports and other constants should be environment variables. 😴

## Credits

- Thanks to the creators and maintainers of https://www.npmjs.com/package/node-rtsp-stream and https://github.com/phoboslab/jsmpeg.

## Notes

This repository includes a copy of `node-rtsp-stream` for my convenience (I keep tweaking some ffmpeg parameters).
