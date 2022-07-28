subtitle

2022-01-03

------------------------------------------------------------------------

title: bluebird.js category: JavaScript libraries

weight: -1

------------------------------------------------------------------------

### Also see

Also see the [promise cheatsheet](promise.html) and [Bluebird.js API](https://github.com/petkaantonov/bluebird/blob/master/API.md) (github.com).

### Example

    promise
      .then(okFn, errFn)
      .spread(okFn, errFn)        // *
      .catch(errFn)
      .catch(TypeError, errFn)    // *
      .finally(fn)
      .map(function (e) { ··· })  // *
      .each(function (e) { ··· }) // *

Those marked with `*` are non-standard Promise API that only work with Bluebird promises.

### Multiple return values

    .then(function () {
      return [ 'abc', 'def' ]
    })
    .spread(function (abc, def) {
      ···
    })

{: data-line=“4”}

Use [Promise.spread](http://bluebirdjs.com/docs/api/promise.spread.html)

### Multiple promises

    Promise.join(
      getPictures(),
      getMessages(),
      getTweets(),
      function (pics, msgs, tweets) {
        return ···
      }
    )

{: data-line=“1”}

Use [Promise.join](http://bluebirdjs.com/docs/api/promise.join.html)

### Multiple promises (array)

-   [Promise.all](http://bluebirdjs.com/docs/api/promise.all.html)(\[p\]) - expect all to pass
-   [Promise.some](http://bluebirdjs.com/docs/api/promise.some.html)(\[p\], count) - expect `count` to pass
-   [Promise.any](http://bluebirdjs.com/docs/api/promise.any.html)(\[p\]) - same as `some([p], 1)`
-   [Promise.race](http://bluebirdjs.com/docs/api/promise.race.html)(\[p\], count) - use `.any` instead
-   [Promise.map](http://bluebirdjs.com/docs/api/promise.map.html)(\[p\], fn, options) - supports concurrency

    Promise.all([promise1, promise2]).then((results) => {
        results[0];
        results[1];
    });

    // succeeds if one succeeds first
    Promise.any(promises).then((results) => {});

{: data-line=“1,8”}

    Promise.map(urls, url => fetch(url))
      .then(···)

{: data-line=“1”}

Use [Promise.map](http://bluebirdjs.com/docs/api/promise.map.html) to “promisify” a list of values.

### Object

    Promise.props({
        photos: get('photos'),
        posts: get('posts')
    }).then((res) => {
        res.photos;
        res.posts;
    });

{: data-line=“1”}

Use [Promise.props](http://bluebirdjs.com/docs/api/promise.props.html).

### Chain of promises

------------------------------------------------------------------------


    function getPhotos() {
      return Promise.try(() => {
        if (err) throw new Error("boo")
        return result
      })
    }

    getPhotos().then(···)

{: data-line=“2”}

Use [Promise.try](http://bluebirdjs.com/docs/api/promise.try.html).

### Node-style functions

    var readFile = Promise.promisify(fs.readFile);
    var fs = Promise.promisifyAll(require('fs'));

{: data-line=“2”}

See [Promisification](http://bluebirdjs.com/docs/api/promisification.html).

### Promise-returning methods

    User.login = Promise.method((email, password) => {
        if (!valid) throw new Error('Email not valid');

        return; /* promise */
    });

{: data-line=“1”}

See [Promise.method](http://bluebirdjs.com/docs/api/promise.method.html).

### Generators

    User.login = Promise.coroutine(function* (email, password) {
        let user = yield User.find({ email: email }).fetch();
        return user;
    });

{: data-line=“1”}

See [Promise.coroutine](http://bluebirdjs.com/docs/api/promise.coroutine.html).

Reference
---------

<a href="http://bluebirdjs.com/docs/api-reference.html" class="uri">http://bluebirdjs.com/docs/api-reference.html</a>