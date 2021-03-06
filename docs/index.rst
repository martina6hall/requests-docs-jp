.. Requests documentation master file, created by
   sphinx-quickstart on Sun Feb 13 23:54:25 2011.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. Requests: HTTP for Humans
   =========================

Requests: 人間のためのHTTP
============================

.. Release v\ |version|. (:ref:`Installation <install>`)

リリース v\ |version|. (:ref:`Installation <install>`)

.. Requests is an :ref:`Apache2 Licensed <apache2>` HTTP library, written in Python, for human beings.

Requestsは、人が使いやすいように設計されていて、Pythonで書かれている :ref:`Apache2 Licensed <apache2>` ベースのHTTPライブラリです。

.. Python's standard **urllib2** module provides most of
   the HTTP capabilities you need, but the API is thoroughly **broken**.
   It was built for a different time — and a different web. It requires an *enormous* amount of work (even method overrides) to perform the simplest of tasks.

Pythonの標準の **urllib2** モジュールは、必要とされるほとんどのHTTPの機能を備えていますが、APIがまともに **使えません** 。
様々なウェブ用途に合わせて作られていて、何回も修正されてきました。
簡単なことを行う(メソッドの上書きでさえ)のに、 *かなり* の量の作業が必要になります。

.. Things shouldn’t be this way. Not in Python.

それはPython的ではないので、そんなに複雑にするべきではありません。

::

    >>> r = requests.get('https://api.github.com/user', auth=('user', 'pass'))
    >>> r.status_code
    200
    >>> r.headers['content-type']
    'application/json; charset=utf8'
    >>> r.encoding
    'utf-8'
    >>> r.text
    u'{"type":"User"...'
    >>> r.json()
    {u'private_gists': 419, u'total_private_repos': 77, ...}

.. See `similar code, without Requests <https://gist.github.com/973705>`_.

`Requestsを使わずに同じ事をするためのコード <https://gist.github.com/973705>`_ を見て下さい。

.. Requests takes all of the work out of Python HTTP/1.1 — making your integration with web services seamless. There's no need to manually add query strings to your URLs, or to form-encode your POST data. Keep-alive and HTTP connection pooling are 100%  automatic, powered by `urllib3 <https://github.com/shazow/urllib3>`_, which is embedded within Requests.

Requestsは、ウェブサービスとシームレスに統合されたPythonのHTTP/1.1の処理の全てを受け持ちます。
URLに手動でクエリを入力したり、POSTデータをエンコードしたりする必要はありません。
Keep-aliveやHTTP接続のプーリングは、Requestsに `urllib3 <https://github.com/shazow/urllib3>`_ が組み込まれているので、100%自動で行われます。


.. Testimonials
   ------------

推薦文
---------------

.. Amazon, Google, Twilio, Mozilla, Heroku, PayPal, NPR, Obama for America, Transifex, Native Instruments, The Washington Post, Twitter, SoundCloud, Kippt, Readability, and Federal US Institutions use Requests internally. It has been downloaded over 1,500,000 times from PyPI.

Amazon、Google、Twilio, Mozilla, Heroku, PayPal, NPR, Obama for America, Transifex, Native Instruments, The Washington Post, Twitter, SoundCloud、Kippt、Readability、Federal US Institutions
は内部でRequestsを使っています。PyPIから1,500,000回以上インストールされました。

**Armin Ronacher**
    .. Requests is the perfect example how beautiful an API can be with the
       right level of abstraction.

    Requestsは、どのようにして綺麗なAPIを正しく抽象化できるかの完璧な例です。

**Matt DeBoard**
    .. I'm going to get @kennethreitz's Python requests module tattooed
       on my body, somehow. The whole thing.

    @kennethreitz さんのPythonのRequestsモジュールのタトゥーを何とかして体に入れたい。以上。

**Daniel Greenfeld**
    .. Nuked a 1200 LOC spaghetti code library with 10 lines of code thanks to
       @kennethreitz's request library. Today has been AWESOME.

    1200行のスパゲッティーコードのライブラリを数10行くらいのコードにしてくれた@kennethreitzのリクエストライブラリに感謝しています。
    すばらしくなりました。

**Kenny Meyers**
    .. Python HTTP: When in doubt, or when not in doubt, use Requests. Beautiful,
       simple, Pythonic.

    PythonのHTTPの実装: 使うか迷ったときも、そうでない時も、Requestsを使います。綺麗な設計で、シンプルで、Pythonicだ。


.. Feature Support
   ---------------

サポートする機能
------------------

.. Requests is ready for today's web.

Requestsは、今日(こんにち)のウェブに欠かせない機能を持っています。

.. International Domains and URLs
.. Keep-Alive & Connection Pooling
.. Sessions with Cookie Persistence
.. Browser-style SSL Verification
.. Basic/Digest Authentication
.. Elegant Key/Value Cookies
.. Automatic Decompression
.. Unicode Response Bodies
.. Multipart File Uploads
.. Connection Timeouts
.. ``.netrc`` support
.. Python 2.6—3.3
.. Thread-safe.

- ドメインとURLの国際化
- Keep-Aliveとコネクションプーリング
- Cookieによるセッションの永続化
- ブラウザのようなSSLによる接続
- ベーシック/ダイジェスト認証
- エレガントなキー/バリューによるCookie
- 圧縮の自動的な展開
- レスポンスの本文のユニコード化
- マルチパートファイルのアップロード
- コネクションのタイムアウト
- ``.netrc`` のサポート
- Python 2.6-3.3に対応
- スレッドセーフ


.. User Guide
   ----------

ユーザーガイド
--------------------

.. This part of the documentation, which is mostly prose, begins with some
   background information about Requests, then focuses on step-by-step
   instructions for getting the most out of Requests.

ドキュメントのこの章は、Requestsに関するいくつかのバックグラウンドを紹介します。
それから、Requestsを最大限に使うための説明をステップ・バイ・ステップで紹介することにフォーカスしています。

.. toctree::
   :maxdepth: 2

   user/intro
   user/install
   user/quickstart
   user/advanced
   user/authentication


.. Community Guide
   -----------------

コミュニティガイド
--------------------

.. This part of the documentation, which is mostly prose, details the
   Requests ecosystem and community.

ドキュメントのこの章は、Requestsのエコシステムやコミュニティについて紹介します。

.. toctree::
   :maxdepth: 1

   community/faq
   community/out-there.rst
   community/support
   community/updates

.. API Documentation
   -----------------

APIドキュメント
--------------------

.. If you are looking for information on a specific function, class or method,
   this part of the documentation is for you.

特定の関数やクラスやメソッドの情報を探している場合は、ドキュメントのこの章を見て下さい。

.. toctree::
   :maxdepth: 2

   api


.. Contributor Guide
   -----------------

コントリビューター用のガイド
----------------------------------

.. If you want to contribute to the project, this part of the documentation is for
   you.

プロジェクトに貢献する場合は、ドキュメントのこの章を見て下さい。

.. toctree::
   :maxdepth: 1

   dev/philosophy
   dev/internals
   dev/todo
   dev/authors