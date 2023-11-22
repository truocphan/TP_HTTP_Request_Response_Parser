# TP-HTTP-Request-Response-Parser

<p align="center">
    <a href="https://github.com/truocphan/TP-HTTP-Request-Response-Parser/releases/"><img src="https://img.shields.io/github/release/truocphan/TP-HTTP-Request-Response-Parser" height=30></a>
	<a href="#"><img src="https://img.shields.io/github/downloads/truocphan/TP-HTTP-Request-Response-Parser/total" height=30></a>
	<a href="#"><img src="https://img.shields.io/github/stars/truocphan/TP-HTTP-Request-Response-Parser" height=30></a>
	<a href="#"><img src="https://img.shields.io/github/forks/truocphan/TP-HTTP-Request-Response-Parser" height=30></a>
	<a href="https://github.com/truocphan/TP-HTTP-Request-Response-Parser/issues?q=is%3Aopen+is%3Aissue"><img src="https://img.shields.io/github/issues/truocphan/TP-HTTP-Request-Response-Parser" height=30></a>
	<a href="https://github.com/truocphan/TP-HTTP-Request-Response-Parser/issues?q=is%3Aissue+is%3Aclosed"><img src="https://img.shields.io/github/issues-closed/truocphan/TP-HTTP-Request-Response-Parser" height=30></a>
	<a href="https://pypi.org/project/TP-HTTP-Request-Response-Parser/" target="_blank"><img src="https://img.shields.io/badge/pypi-3775A9?style=for-the-badge&logo=pypi&logoColor=white" height=30></a>
	<a href="https://www.facebook.com/292706121240740" target="_blank"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" height=30></a>
	<a href="https://twitter.com/truocphan" target="_blank"><img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" height=30></a>
	<a href="https://github.com/truocphan" target="_blank"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" height=30></a>
	<a href="mailto:truocphan112017@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" height=30></a>
	<a href="https://www.buymeacoffee.com/truocphan" target="_blank"><img src="https://img.shields.io/badge/Buy_Me_A_Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" height=30></a>
</p>

```
from TP_HTTP_Request_Response_Parser import *

# Parsing HTTP Request
rawRequest = """GET /v1/promo/extension HTTP/2
Host: d2y7f743exec8w.cloudfront.net
Accept-Encoding: gzip, deflate
Accept: */*
Accept-Language: en-US;q=0.9,en;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.5845.97 Safari/537.36
Connection: close
Cache-Control: max-age=0

"""

# RequestParser = TP_HTTP_REQUEST_PARSER(open("request.txt", encoding="utf-8", errors="ignore").read())
RequestParser = TP_HTTP_REQUEST_PARSER(rawRequest, ordered_dict=True)

print("- request_method:", RequestParser.request_method)
print("- request_path:", RequestParser.request_path)
print("- request_query:", RequestParser.request_query.dumps(indent=4))
print("- request_fragment:", RequestParser.request_fragment)
print("- request_headers:", RequestParser.request_headers.dumps(indent=4))
print("- request_body:", RequestParser.request_body.dumps(indent=4))



# Parsing HTTP Response
rawResponse = """HTTP/2 200 OK
Content-Type: application/json; charset=utf-8
Server: nginx
Date: Mon, 21 Aug 2023 03:55:08 GMT
Etag: W/"846e0a9b390c273d2d7a6843085411d1"
Cache-Control: max-age=0, private, must-revalidate
X-Request-Id: 06024e22-f233-4517-b0f6-f444c8464e7b
Strict-Transport-Security: max-age=63072000; includeSubDomains
Strict-Transport-Security: max-age=63072000; preload
Vary: Accept-Encoding,Accept
X-Cache: Miss from cloudfront
Via: 1.1 19175f36fb9c16ba394561bae28598da.cloudfront.net (CloudFront)
X-Amz-Cf-Pop: SGN50-P2
X-Amz-Cf-Id: eKssgTNGDCswPiQtSYFD1MRNBJCTHEbnQp4MQjtQx2B4eM7oqXYIHg==

{"ok":true,"promo":[]}"""

# ResponseParser = TP_HTTP_RESPONSE_PARSER(open("response.txt", encoding="utf-8", errors="ignore").read())
ResponseParser = TP_HTTP_RESPONSE_PARSER(rawResponse, ordered_dict=True)

print("- response_statusCode:", ResponseParser.response_statusCode)
print("- response_statusText:", ResponseParser.response_statusText)
print("- response_headers:", ResponseParser.response_headers.dumps(indent=4))
print("- response_body:", ResponseParser.response_body.dumps(indent=4))
```
