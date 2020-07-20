# MGLTools in Docker

Because MGLTools (AudoDock Tools, Pmv, Vision) [http://mgltools.scripps.edu/] do not run in latest Mac OS any more, this Docker container is created to run them on Mac.

MGLTools are X11 GUI programs, thus, require X Server. Please install X Server on your platform:
- Mac OS: https://www.xquartz.org/
- WIndows: https://sourceforge.net/projects/vcxsrv/
- Linux: Install X11

To run on Mac:
```bash
docker run -ti --rm -e DISPLAY=host.docker.internal:0 -v [your local data directory]:/data kittyjosh111/mgltools:1.5.6
```

To run on Linux or Windows WSL(2):
```bash
docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v [your local data directory]:/data kittyjosh111/mgltools:1.5.6
```
