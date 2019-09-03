# The role of nested functions in JS

The core importance of nested functions is scope generation. We need nested functions and scopes in JavaScript to achieve the following:

* [Non-Polluted Global Namespace](https://stackoverflow.com/questions/8862665/what-does-it-mean-global-namespace-would-be-polluted)
* Modularization of functionality
* Encapsulate private internal workings of modules
* Prevent collision of identifiers across different scripts
* Smaller script sizes due to the fact that variables inside nested scopes qualify for minification.
* It speeds up the [Identifier Resolution Process](http://davidshariff.com/blog/javascript-scope-chain-and-closures/)

Sample module that displays the power of encapsulation offered by function nesting and scopes:

```
var notificationService = (function ($, toastr, undefined) {
    var _externals = {},
        _jqExtend = $.extend;

    /*
     * Private Methods
     */
    function _showMessage(params) {
        params = params || {};
        toastr.remove();

        if (typeof (params.title) === "undefined")
            toastr[params.method](params.msg);
        else
            toastr[params.method](params.msg, params.title);
    }

    /*
     * Public Members
     */
    _externals.clear = function () {
        toastr.remove();
    };

_externals.showError = function (params) {
        params = params || {};

        _jqExtend(params, {
            method: "error"
        });

        _showMessage(params);
    };

    _externals.showInfo = function (params) {
        params = params || {};

        _jqExtend(params, {
            method: "info"
        });

        _showMessage(params);
    };

_externals.showSuccess = function (params) {
        params = params || {};

        _jqExtend(params, {
            method: "success"
        });

        _showMessage(params);
    };

    _externals.showWarning = function (params) {
        params = params || {};

        _jqExtend(params, {
            method: "warning"
        });

        _showMessage(params);
    };

    return _externals;
})(jQuery, toastr);
```

👆 all members attached to the _externals object are exposed to the global namespace via reference to notificationService object. Without using scoping, internal members (_jqExtend and _showMessage) would also be attached to the window object and increase the effort required by the browser to resolve identifier references.

Quoted from [this Stack Overflow answer](https://stackoverflow.com/a/44482736).