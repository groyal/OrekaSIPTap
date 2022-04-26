## Oreka, an opensource VoIP media capture and retrieval platform

Based on [OrecX](http://www.orecx.com/open-source/) [Oreka](https://github.com/OrecX/Oreka), this project tries to provide a complete Call Recording (SIPREC) solution.  

### Components
- **Orkaudio**:  
    The audio capture and storage daemon with pluggable capture modules currently comes with modules for VoIP and sound device recording.

    
### Improvements

**OrkAudio** 

- Support for G729 Codec  
- CallID Tracking   
- Upgrade to latest version of libraries.


### Building

#### Docker

```bash
export DOCKER_BUILDKIT=1
distribution/docker
docker build -f Dockerfile.orkaudio -t voiceip/orkaudio .
docker run -it --net=host --restart=always --privileged=true -v /var/log/orkaudio:/var/log/orkaudio  -v /etc/orkaudio:/etc/orkaudio voiceip/orkaudio:latest 
```

### Distribution & Installation

#### Docker

Docker images are available via [docker hub](https://hub.docker.com/r/voiceip/orkaudio/tags), so just run the below command to pull images directly from hub.docker.com. Note: `--net=host` on docker works on linux systems and is a [limitation of docker](https://docs.docker.com/network/host/), so please keep that in mind.

```bash
docker run -it --net=host --restart=always --privileged=true -v /var/log/orkaudio:/var/log/orkaudio -v /etc/orkaudio:/etc/orkaudio voiceip/orkaudio:latest
```

#### Debian/Ubuntu

Binary releases are available from the [Releases Section](https://github.com/voiceip/oreka/releases). Download and refer to the [installation instructions](https://github.com/voiceip/oreka/wiki/Installation).


