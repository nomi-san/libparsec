# libparsec
⚡ The imaginary Parsec SDK — Low latency, peer-to-peer, interactive game streaming.

## Covered things

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

- [ ] ParsecSignalInit
- [ ] ParsecSignalDestroy
- [ ] ParsecSignalConnect
- [ ] ParsecSignalDisconnect

(Client + Signal API)
- [ ] ParsecClientNewAttempt
- [x] ParsecClientAddCandidate
- [x] ParsecClientBeginP2P
- [ ] ParsecClientEndConnection
