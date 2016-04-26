
set(ENV{INSTALL_DIR} ${proxygen_SOURCE_DIR}/lib/http)
set(ENV{HEADERS_LIST} ${proxygen_SOURCE_DIR}/lib/http/HTTPCommonHeaders.txt)
set(ENV{FBCODE_DIR} ${proxygen_SOURCE_DIR}/..)
execute_process( COMMAND ${proxygen_SOURCE_DIR}/lib/http/gen_HTTPCommonHeaders.h.sh )
execute_process( COMMAND ${proxygen_SOURCE_DIR}/lib/http/gen_HTTPCommonHeaders.cpp.sh )

add_library(proxygenhttp
	HTTPCommonHeaders.cpp 
	codec/CodecProtocol.cpp 
	codec/compress/GzipHeaderCodec.cpp 
	codec/compress/HeaderTable.cpp 
	codec/compress/HPACKCodec.cpp 
	codec/compress/HPACKContext.cpp 
	codec/compress/HPACKDecodeBuffer.cpp 
	codec/compress/HPACKDecoder.cpp 
	codec/compress/HPACKEncodeBuffer.cpp 
	codec/compress/HPACKEncoder.cpp 
	codec/compress/HPACKHeader.cpp 
	codec/compress/Huffman.cpp 
	codec/compress/Logging.cpp 
	codec/compress/StaticHeaderTable.cpp 
	codec/compress/experimental/hpack9/HPACKCodec.cpp 
	codec/compress/experimental/hpack9/HPACKDecoder.cpp 
	codec/compress/experimental/hpack9/HPACKEncoder.cpp 
	codec/compress/experimental/hpack9/Huffman.cpp 
	codec/compress/experimental/hpack9/StaticHeaderTable.cpp 
	codec/ErrorCode.cpp 
	codec/HTTP2Codec.cpp 
	codec/HTTP2Constants.cpp 
	codec/HTTP2Framer.cpp 
	codec/FlowControlFilter.cpp 
	codec/HTTP1xCodec.cpp 
	codec/HTTPChecks.cpp 
	codec/HTTPCodecFactory.cpp 
	codec/HTTPCodecFilter.cpp 
	codec/HTTPCodecPrinter.cpp 
	codec/HTTPSettings.cpp 
	codec/SPDYCodec.cpp 
	codec/HTTPParallelCodec.cpp 
	codec/SPDYConstants.cpp 
	codec/SPDYUtil.cpp 
	codec/SettingsId.cpp 
	codec/TransportDirection.cpp 
	HTTPConnector.cpp 
	HTTPConstants.cpp 
	HTTPException.cpp 
	HTTPHeaders.cpp 
	HTTPMessage.cpp 
	HTTPMethod.cpp 
	ProxygenErrorEnum.cpp 
	RFC2616.cpp 
	session/ByteEvents.cpp 
	session/CodecErrorResponseHandler.cpp 
	session/HTTPDefaultSessionCodecFactory.cpp 
	session/HTTPDirectResponseHandler.cpp 
	session/HTTPDownstreamSession.cpp 
	session/HTTPErrorPage.cpp 
	session/HTTPEvent.cpp 
	session/HTTPSessionAcceptor.cpp 
	session/HTTPSession.cpp 
	session/HTTPTransaction.cpp 
	session/HTTPTransactionEgressSM.cpp 
	session/HTTPTransactionIngressSM.cpp 
	session/HTTPUpstreamSession.cpp 
	session/HTTP2PriorityQueue.cpp 
	session/ByteEventTracker.cpp 
	session/SimpleController.cpp 
	session/TransportFilter.cpp 
	Window.cpp
)
