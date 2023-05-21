WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
[parallels@fedora module_08]$ cat ~/log.md 
INFO:     172.20.0.1:59014 - &quot;GET / HTTP/1.1&quot; 404 Not Found
INFO:     172.20.0.1:59018 - &quot;GET /1 HTTP/1.1&quot; 404 Not Found
INFO:     172.20.0.1:59022 - &quot;GET /5 HTTP/1.1&quot; 404 Not Found
INFO:     172.20.0.1:59026 - &quot;GET / HTTP/1.1&quot; 404 Not Found
INFO:     172.20.0.1:59032 - &quot;GET /presentationsAndAuthor/1 HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59038 - &quot;GET /presentationsAndAuthor/5 HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59044 - &quot;GET /presentationsAndAuthor/10 HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59050 - &quot;GET /presentationsAndAuthor/sd HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59056 - &quot;GET /presentationsAndAuthor/aasdd HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59138 - &quot;GET /presenationsAndAuthor/asd HTTP/1.1&quot; 404 Not Found
INFO:     172.20.0.1:59142 - &quot;GET /presenationsAndAuthor/1 HTTP/1.1&quot; 404 Not Found
INFO:     172.20.0.1:59146 - &quot;GET /presentationsAndAuthor/1 HTTP/1.1&quot; 500 Internal Server Error
Moore
INFO:     172.20.0.1:59154 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59162 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59170 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59178 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59186 - &quot;GET /presentationsAndAuthor/1 HTTP/1.1&quot; 500 Internal Server Error
Moore
INFO:     172.20.0.1:59192 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59200 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59208 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59216 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59224 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59232 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59238 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59244 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59250 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59256 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59262 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59268 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59274 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59280 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59286 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59292 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59298 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59304 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59310 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59316 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59322 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59328 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59334 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59340 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59348 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59356 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59362 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59368 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59374 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59382 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
INFO:     172.20.0.1:59388 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
INFO:     172.20.0.1:59394 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59400 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59408 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
[parallels@fedora module_08]$ sudo docker logs service_main
INFO:     Will watch for changes in these directories: [&apos;/&apos;]
INFO:     Uvicorn running on http://0.0.0.0:8083 (Press CTRL+C to quit)
INFO:     Started reloader process [1] using WatchFiles
Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/runpy.py&quot;, line 196, in _run_module_as_main
    return _run_code(code, main_globals, None,
  File &quot;/usr/lib/python3.10/runpy.py&quot;, line 86, in _run_code
    exec(code, run_globals)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/__main__.py&quot;, line 4, in &lt;module&gt;
    uvicorn.main()
  File &quot;/usr/local/lib/python3.10/dist-packages/click/core.py&quot;, line 1130, in __call__
    return self.main(*args, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/click/core.py&quot;, line 1055, in main
    rv = self.invoke(ctx)
  File &quot;/usr/local/lib/python3.10/dist-packages/click/core.py&quot;, line 1404, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File &quot;/usr/local/lib/python3.10/dist-packages/click/core.py&quot;, line 760, in invoke
    return __callback(*args, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/main.py&quot;, line 404, in main
    run(
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/main.py&quot;, line 564, in run
    ChangeReload(config, target=server.run, sockets=[sock]).run()
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/supervisors/basereload.py&quot;, line 45, in run
    for changes in self:
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/supervisors/basereload.py&quot;, line 64, in __next__
    return self.should_restart()
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/supervisors/watchfilesreload.py&quot;, line 85, in should_restart
    changes = next(self.watcher)
  File &quot;/usr/local/lib/python3.10/dist-packages/watchfiles/main.py&quot;, line 119, in watch
    with RustNotify([str(p) for p in paths], debug, force_polling, poll_delay_ms, recursive) as watcher:
FileNotFoundError: Permission denied (os error 13) about [&quot;/proc&quot;]
INFO:     Started server process [7]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59014 - &quot;GET / HTTP/1.1&quot; 404 Not Found
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59018 - &quot;GET /1 HTTP/1.1&quot; 404 Not Found
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59022 - &quot;GET /5 HTTP/1.1&quot; 404 Not Found
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59026 - &quot;GET / HTTP/1.1&quot; 404 Not Found
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59032 - &quot;GET /presentationsAndAuthor/1 HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59038 - &quot;GET /presentationsAndAuthor/5 HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59044 - &quot;GET /presentationsAndAuthor/10 HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59050 - &quot;GET /presentationsAndAuthor/sd HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59056 - &quot;GET /presentationsAndAuthor/aasdd HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59138 - &quot;GET /presenationsAndAuthor/asd HTTP/1.1&quot; 404 Not Found
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59142 - &quot;GET /presenationsAndAuthor/1 HTTP/1.1&quot; 404 Not Found
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59146 - &quot;GET /presentationsAndAuthor/1 HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59154 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59162 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59170 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59178 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
INFO:     172.20.0.1:59186 - &quot;GET /presentationsAndAuthor/1 HTTP/1.1&quot; 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 184, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 79, in __call__
    raise exc
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 21, in __call__
    raise e
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 104, in read_presentation
    presentation = get_presentation(title)
  File &quot;/./service_main.py&quot;, line 66, in get_presentation
    presentation = Presentation(**response_presentation.json()[0])
IndexError: list index out of range
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59192 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59200 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59208 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
Moore
INFO:     172.20.0.1:59216 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59224 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb520&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
INFO:     172.20.0.1:59232 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
INFO:     172.20.0.1:59238 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e620a1a0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
INFO:     172.20.0.1:59244 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e61eb280&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

INFO:     172.20.0.1:59250 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df550&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
INFO:     172.20.0.1:59256 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60dfaf0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59262 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59268 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59274 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59280 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59286 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59292 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59298 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59304 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59310 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
INFO:     172.20.0.1:59316 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804340&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59322 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59328 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59334 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 6
WARNING:root:
Moore
INFO:     172.20.0.1:59340 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59348 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e58055d0&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
INFO:     172.20.0.1:59356 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 1
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
INFO:     172.20.0.1:59362 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e60df490&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 2
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
INFO:     172.20.0.1:59368 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5805c60&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 3
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
INFO:     172.20.0.1:59374 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5806b30&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 4
WARNING:root:
--- Logging error ---
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 174, in _new_conn
    conn = connection.create_connection(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/connection.py&quot;, line 72, in create_connection
    for res in socket.getaddrinfo(host, port, family, socket.SOCK_STREAM):
  File &quot;/usr/lib/python3.10/socket.py&quot;, line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 703, in urlopen
    httplib_response = self._make_request(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 398, in _make_request
    conn.request(method, url, **httplib_request_kw)
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 239, in request
    super(HTTPConnection, self).request(method, url, body=body, headers=headers)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1282, in request
    self._send_request(method, url, body, headers, encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1328, in _send_request
    self.endheaders(body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1277, in endheaders
    self._send_output(message_body, encode_chunked=encode_chunked)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 1037, in _send_output
    self.send(msg)
  File &quot;/usr/lib/python3.10/http/client.py&quot;, line 975, in send
    self.connect()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 205, in connect
    conn = self._new_conn()
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connection.py&quot;, line 186, in _new_conn
    raise NewConnectionError(
urllib3.exceptions.NewConnectionError: &lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 489, in send
    resp = conn.urlopen(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/connectionpool.py&quot;, line 787, in urlopen
    retries = retries.increment(
  File &quot;/usr/local/lib/python3.10/dist-packages/urllib3/util/retry.py&quot;, line 592, in increment
    raise MaxRetryError(_pool, url, error or ResponseError(cause))
urllib3.exceptions.MaxRetryError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/./service_main.py&quot;, line 74, in get_author
    response_author = requests.get(&quot;http://&quot; + service_author + &quot;/authors/&quot; + str(id))
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 73, in get
    return request(&quot;get&quot;, url, params=params, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/api.py&quot;, line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 587, in request
    resp = self.send(prep, **send_kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/sessions.py&quot;, line 701, in send
    r = adapter.send(request, **kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/requests/adapters.py&quot;, line 565, in send
    raise ConnectionError(e, request=request)
requests.exceptions.ConnectionError: HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 1100, in emit
    msg = self.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 943, in format
    return fmt.format(record)
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 678, in format
    record.message = record.getMessage()
  File &quot;/usr/lib/python3.10/logging/__init__.py&quot;, line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File &quot;&lt;string&gt;&quot;, line 1, in &lt;module&gt;
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 116, in spawn_main
    exitcode = _main(fd, parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/spawn.py&quot;, line 129, in _main
    return self._bootstrap(parent_sentinel)
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 314, in _bootstrap
INFO:     172.20.0.1:59382 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 500 Internal Server Error
    self.run()
  File &quot;/usr/lib/python3.10/multiprocessing/process.py&quot;, line 108, in run
    self._target(*self._args, **self._kwargs)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/_subprocess.py&quot;, line 76, in subprocess_started
    target(sockets=sockets)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/server.py&quot;, line 60, in run
    return asyncio.run(self.serve(sockets=sockets))
  File &quot;/usr/lib/python3.10/asyncio/runners.py&quot;, line 44, in run
    return loop.run_until_complete(main)
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 633, in run_until_complete
    self.run_forever()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 600, in run_forever
    self._run_once()
  File &quot;/usr/lib/python3.10/asyncio/base_events.py&quot;, line 1896, in _run_once
    handle._run()
  File &quot;/usr/lib/python3.10/asyncio/events.py&quot;, line 80, in _run
    self._context.run(self._callback, *self._args)
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/httptools_impl.py&quot;, line 419, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File &quot;/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py&quot;, line 78, in __call__
    return await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/applications.py&quot;, line 271, in __call__
    await super().__call__(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/applications.py&quot;, line 118, in __call__
    await self.middleware_stack(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py&quot;, line 162, in __call__
    await self.app(scope, receive, _send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py&quot;, line 68, in __call__
    await self.app(scope, receive, sender)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py&quot;, line 18, in __call__
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 706, in __call__
    await route.handle(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 276, in handle
    await self.app(scope, receive, send)
  File &quot;/usr/local/lib/python3.10/dist-packages/starlette/routing.py&quot;, line 66, in app
    response = await func(request)
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 237, in app
    raw_response = await run_endpoint_function(
  File &quot;/usr/local/lib/python3.10/dist-packages/fastapi/routing.py&quot;, line 163, in run_endpoint_function
    return await dependant.call(**values)
  File &quot;/./service_main.py&quot;, line 105, in read_presentation
    author = get_author(presentation.author_id)
  File &quot;/./circuitbreaker.py&quot;, line 159, in wrapper
    return call(function, *args, **kwargs)
  File &quot;/./circuitbreaker.py&quot;, line 170, in call
    return func(*args, **kwargs)
  File &quot;/./service_main.py&quot;, line 76, in get_author
    logging.warning(&quot;&gt;&gt;&gt; Error Connecting:&quot;, errc)
Message: &apos;&gt;&gt;&gt; Error Connecting:&apos;
Arguments: (ConnectionError(MaxRetryError(&quot;HTTPConnectionPool(host=&apos;service_author&apos;, port=8081): Max retries exceeded with url: /authors/1 (Caused by NewConnectionError(&apos;&lt;urllib3.connection.HTTPConnection object at 0x7fa2e5804940&gt;: Failed to establish a new connection: [Errno -2] Name or service not known&apos;))&quot;)),)
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59388 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;open&quot;, failures: 5
WARNING:root:
CRITICAL:root:Circuit OPEN
INFO:     172.20.0.1:59394 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;half_open&quot;, failures: 5
WARNING:root:
Moore
INFO:     172.20.0.1:59400 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
Moore
INFO:     172.20.0.1:59408 - &quot;GET /presentationsAndAuthor/First%20Presentation HTTP/1.1&quot; 200 OK
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
WARNING:root:Circuit &quot;get_author&quot; is &quot;closed&quot;, failures: 0
WARNING:root:
</pre>