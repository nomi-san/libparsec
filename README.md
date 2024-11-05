<br />

<p align="center">
    <img src="https://github.com/user-attachments/assets/1d8b571d-280c-4f1f-bbca-aa55a96783f4" width="120" />
    <h1 align="center">libparsec</h1>
    <p align="center">⚡ The imaginary Parsec SDK<br />Low latency, peer-to-peer, interactive game streaming.</p>
</p>

<br />

## 🚧 Working in progress

The goal is single header for C/C++, and Rust bindings. Output binaries would be static lib and dynamic lib (DLL).

> F**k this $320M acquisition!

### Target platforms

- [x] Windows (64-bit)
- [ ] Linux
- [ ] macOS 

### Client features

- [x] Hardware decoders
- [x] FFmpeg decoder (smaller build)
- [x] HEVC codec 
- [x] YUV420, YUV444
- [x] 10-bit color

### Instance functions

- [x] ParsecInit
- [x] ParsecDestroy
- [x] ParsecGetConfig
- [x] ParsecGetBuffer
- [x] ParsecFree
- [x] ParsecSetLogCallback
- [x] ParsecVersion
- [x] ParsecGetOutputs
- [ ] ParsecGetAudioOutputs
- [x] ParsecGetDecoders
- [x] ParsecJSONCommand
- [x] ParsecCanHost
- [ ] ~~ParsecGetVUSBState~~ (not supported)
- [ ] ~~ParsecGetVDDState~~ (not supported)
- [ ] ParsecSetConfig

### Client functions

- [x] ParsecClientConnect (removed in new SDK)
- [x] ParsecClientDisconnect
- [x] ParsecClientGetStatus
- [x] ParsecClientGetGuests
- [x] ParsecClientSetConfig
- [x] ParsecClientSetDimensions
- [x] ParsecClientPollFrame
- [x] ParsecClientPollAudio
- [x] ParsecClientPollEvents
- [ ] ~~ParsecClientGLDestroy~~ (deprecated)
- [x] ParsecClientSendMessage
- [ ] ParsecClientPause
- [x] ParsecClientEnableStream
- [x] ParsecClientSendUserData
- [x] ParsecClientSendExtraData
- [ ] ~~ParsecClientScalePenMessage~~ (not supported)
- [ ] ~~ParsecClientSendVirtualUSB~~ (not supported)

### Host functions

(not implemented yet)

### Signal functions

[Signal server](https://support.parsec.app/hc/en-us/articles/4423453624077-Components-and-Connection-Sequence) and these functions are used to control the handshake flow.<br/>
This is a way to build your own server without relying on the Parsec's online service.

```mermaid
sequenceDiagram
    participant Client
    participant STUN_Server as STUN Server
    participant Host
    participant Signal_API as Signal API
    
    Client->>STUN_Server: Start UDP conversation (port 3478)
    STUN_Server-->>Client: Respond with public IP & listener port
    Client->>Signal_API: Send connection info via WebSocket
    Host->>STUN_Server: Start UDP conversation (port 3478)
    STUN_Server-->>Host: Respond with public IP & listener port
    Host->>Signal_API: Send connection info via WebSocket
    Signal_API-->>Client: Host's connection info
    Signal_API-->>Host: Client's connection info
    Client->>Host: Attempt connection
    Host->>Client: Attempt connection
    Note over Client, Host: Connection established based on NAT traversal success

```

- [x] ParsecSignalInit
- [x] ParsecSignalDestroy
- [x] ParsecSignalConnect
- [x] ParsecSignalDisconnect
- [x] ParsecSignalSendCandidate
- [ ] ParsecClientNewAttempt
- [x] ParsecClientAddCandidate
- [x] ParsecClientBeginP2P
- [ ] ParsecClientEndConnection
