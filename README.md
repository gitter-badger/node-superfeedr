## Modules

<dl>
<dt><a href="#module_superfeedr">superfeedr</a></dt>
<dd><p>node-superfeedr</p>
<p>Install:</p>
<pre><code class="lang-bash">npm install node-superfeedr
</code></pre>
<p>Example:</p>
<pre><code class="lang-javascript">var superfeedr = require(&#39;node-superfeedr&#39;);
</code></pre>
</dd>
<dt><a href="#module_superfeedr/subscribers/http">superfeedr/subscribers/http</a></dt>
<dd><p>Superfeedr Subscribers Http Client</p>
<p>Example:</p>
<pre><code class="lang-javascript">var superfeedr = require(&#39;node-superfeedr&#39;);
var options = {
  username: process.env.SUPERFEEDR_USERNAME || &#39;username&#39;,
  token: process.env.SUPERFEEDR_TOKEN || &#39;token&#39;
};

var client = new superfeedr.Subscribers.HttpClient(options);
</code></pre>
</dd>
</dl>

<a name="module_superfeedr"></a>
## superfeedr
node-superfeedr

Install:

```bash
npm install node-superfeedr
```

Example:

```javascript
var superfeedr = require('node-superfeedr');
```

<a name="module_superfeedr/subscribers/http"></a>
## superfeedr/subscribers/http
Superfeedr Subscribers Http Client

Example:

```javascript
var superfeedr = require('node-superfeedr');
var options = {
  username: process.env.SUPERFEEDR_USERNAME || 'username',
  token: process.env.SUPERFEEDR_TOKEN || 'token'
};

var client = new superfeedr.Subscribers.HttpClient(options);
```

**Submodule**: http  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>Object</code> | override default options |
| options.username | <code>string</code> | Superfeedr username | default: process.env.SUPERFEEDR_USERNAME |
| options.token | <code>string</code> | Superfeedr token value | default: process.env.SUPERFEEDR_TOKEN |
| options.endpoint | <code>url</code> | Superfeedr Push Api Endpoint | default: https://push.superfeedr.com |


* [superfeedr/subscribers/http](#module_superfeedr/subscribers/http)
    * [~addFeed(topic, callback, [secret], [options])](#module_superfeedr/subscribers/http..addFeed) ⇒ <code>Promise</code>
    * [~removeFeed(topic, [callback], [options])](#module_superfeedr/subscribers/http..removeFeed) ⇒ <code>Promise</code>

<a name="module_superfeedr/subscribers/http..addFeed"></a>
### superfeedr/subscribers/http~addFeed(topic, callback, [secret], [options]) ⇒ <code>Promise</code>
**Kind**: inner method of <code>[superfeedr/subscribers/http](#module_superfeedr/subscribers/http)</code>  

| Param | Type | Description |
| --- | --- | --- |
| topic | <code>url</code> | The URL of the HTTP resource to which you want to subscribe. It cannot be more than 2048 characters long. |
| callback | <code>url</code> | The webhook: it's the URL to which notifications will be sent. Make sure you it's web-accessible, ie not behind a firewall. Its size is currently limited to 250 characters. |
| [secret] | <code>string</code> | Recommended. A unique secret string which will be used by us to compute a signature. You should check this signature when getting notifications. |
| [options] | <code>Object</code> | Less used options |
| options.verify | <code>string</code> | Will perform a PubSubHubbub verification of intent synschronously or asynschronously | async &#124; sync. |
| options.format | <code>string</code> | If you want to receive notifications as json format (for feeds only!). You can also use an Accept HTTP header like this: Accept: application/json. If you explicitly want to receive notification as Atom. This is used by default for any resource that's either Atom or RSS.   If you don't specify any, we will send you the data pulled from the HTTP resource, (excluding feeds). | json &#124; atom. |
| options.retrieve | <code>string</code> | If set to true, the response will include the current representation of the feed as stored in Superfeedr, in the format desired. Please check our Schema for more details. | true &#124; false |

<a name="module_superfeedr/subscribers/http..removeFeed"></a>
### superfeedr/subscribers/http~removeFeed(topic, [callback], [options]) ⇒ <code>Promise</code>
**Kind**: inner method of <code>[superfeedr/subscribers/http](#module_superfeedr/subscribers/http)</code>  

| Param | Type | Description |
| --- | --- | --- |
| topic | <code>url</code> | The URL of the HTTP resource to which you want to unsubscribe. |
| [callback] | <code>url</code> | The URL to which notifications will be sent. It is optional if you are only subscribed to the feed 'once', with a single hub.callback. If you have multiple subscriptions, you will need to supply the hub.callback parameter. It is also required if you use the hub.verify param. |
| [options] | <code>Object</code> | Less used options |
| options.verify | <code>string</code> | We will perform a PubSubHubbub verification of intent synschronously or asynschronously. | async &#124; sync |

