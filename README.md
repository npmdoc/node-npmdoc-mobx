# api documentation for  [mobx (v3.1.8)](https://mobxjs.github.io/mobx)  [![npm package](https://img.shields.io/npm/v/npmdoc-mobx.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-mobx) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-mobx.svg)](https://travis-ci.org/npmdoc/node-npmdoc-mobx)
#### Simple, scalable state management.

[![NPM](https://nodei.co/npm/mobx.png?downloads=true)](https://www.npmjs.com/package/mobx)

[![apidoc](https://npmdoc.github.io/node-npmdoc-mobx/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-mobx_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-mobx/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-mobx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-mobx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Michel Weststrate"
    },
    "bugs": {
        "url": "https://github.com/mobxjs/mobx/issues"
    },
    "dependencies": {},
    "description": "Simple, scalable state management.",
    "devDependencies": {
        "babel-cli": "^6.4.5",
        "babel-core": "^6.4.5",
        "babel-plugin-transform-decorators-legacy": "^1.3.4",
        "babel-preset-es2015": "^6.3.13",
        "babel-preset-react": "^6.3.13",
        "babel-preset-stage-1": "^6.3.13",
        "babelify": "^7.3.0",
        "browserify": "^12.0.1",
        "coveralls": "^2.11.4",
        "faucet": "0.0.1",
        "flow-bin": "0.36.0",
        "istanbul": "^0.3.21",
        "iterall": "^1.0.2",
        "lodash.intersection": "^3.2.0",
        "ncp": "^2.0.0",
        "rimraf": "^2.5.4",
        "tape": "^4.2.2",
        "tape-run": "^2.1.0",
        "typescript": "^2.1.4",
        "uglify-js": "^2.6.1"
    },
    "directories": {},
    "dist": {
        "shasum": "94a24ce41baa9d0ccf3bd71b17dbe093bb0e1b05",
        "tarball": "https://registry.npmjs.org/mobx/-/mobx-3.1.8.tgz"
    },
    "files": [
        "lib",
        "LICENSE",
        "bower.json"
    ],
    "gitHead": "bb5baf2cb55b8687adbf6caf4f61d1083947266d",
    "homepage": "https://mobxjs.github.io/mobx",
    "keywords": [
        "mobx",
        "mobservable",
        "observable",
        "react-component",
        "react",
        "reactjs",
        "reactive",
        "model",
        "frp",
        "functional-reactive-programming",
        "state management",
        "data flow"
    ],
    "license": "MIT",
    "main": "lib/mobx.js",
    "maintainers": [
        {
            "name": "mweststrate",
            "email": "mweststrate@gmail.com"
        }
    ],
    "name": "mobx",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/mobxjs/mobx.git"
    },
    "scripts": {
        "_prepublish": "npm run small-build",
        "build-babel-tests": "babel test/babel/babel-tests.js -o test/babel-tests.js",
        "build-tests": "npm run build-typescript-tests && npm run build-babel-tests",
        "build-typescript-tests": "tsc -p test/typescript",
        "coverage": "npm run quick-build && npm run build-tests && istanbul cover tape test/*.js test/typescript/typescript-tests.js",
        "full-test": "npm run small-build && npm run build-tests && npm run use-minified && npm run tape && node --expose-gc test/perf/index.js && npm run test-flow && node test/mixed-versions/mixed-versions.js",
        "lint": "tslint -c tslint.json src/*.ts src/types/*.ts src/api/*.ts src/core/*.ts src/utils/*.ts",
        "perf": "npm run small-build && PERSIST=true time node --expose-gc test/perf/index.js",
        "quick-build": "tsc --pretty",
        "small-build": "node scripts/single-file-build.js",
        "tape": "tape test/*.js test/typescript/typescript-tests.js | faucet",
        "test": "npm run quick-build && npm run tape",
        "test-browser-chrome": "npm run small-build && ( browserify test/*.js | tape-run --browser chrome | faucet )",
        "test-browser-electron": "npm run small-build && ( browserify test/*.js | tape-run | faucet )",
        "test-browser-firefox": "npm run small-build && ( browserify test/*.js  | tape-run --browser firefox | faucet )",
        "test-browser-safari": "npm run small-build && ( browserify test/*.js -t [ babelify --presets [ es2015 ] ] | tape-run --browser safari | faucet )",
        "test-flow": "flow check",
        "test-travis": "npm run full-test && npm run quick-build && istanbul cover tape test/*.js test/typescript/typescript-tests.js",
        "use-minified": "cp lib/mobx.min.js lib/mobx.js"
    },
    "typings": "lib/mobx.d.ts",
    "umd:main": "lib/mobx.umd.js",
    "version": "3.1.8"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module mobx](#apidoc.module.mobx)
1.  [function <span class="apidocSignatureSpan">mobx.</span>Atom (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.Atom)
1.  [function <span class="apidocSignatureSpan">mobx.</span>BaseAtom (name)](#apidoc.element.mobx.BaseAtom)
1.  [function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories ()](#apidoc.element.mobx.IObservableFactories)
1.  [function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories.prototype.deep ()](#apidoc.element.mobx.IObservableFactories.prototype.deep)
1.  [function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories.prototype.ref ()](#apidoc.element.mobx.IObservableFactories.prototype.ref)
1.  [function <span class="apidocSignatureSpan">mobx.</span>ObservableMap (initialData, enhancer, name)](#apidoc.element.mobx.ObservableMap)
1.  [function <span class="apidocSignatureSpan">mobx.</span>Reaction (name, onInvalidate)](#apidoc.element.mobx.Reaction)
1.  [function <span class="apidocSignatureSpan">mobx.</span>action (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.action)
1.  [function <span class="apidocSignatureSpan">mobx.</span>asFlat (value)](#apidoc.element.mobx.asFlat)
1.  [function <span class="apidocSignatureSpan">mobx.</span>asMap (data)](#apidoc.element.mobx.asMap)
1.  [function <span class="apidocSignatureSpan">mobx.</span>asReference (value)](#apidoc.element.mobx.asReference)
1.  [function <span class="apidocSignatureSpan">mobx.</span>asStructure (value)](#apidoc.element.mobx.asStructure)
1.  [function <span class="apidocSignatureSpan">mobx.</span>autorun (arg1, arg2, arg3)](#apidoc.element.mobx.autorun)
1.  [function <span class="apidocSignatureSpan">mobx.</span>autorunAsync (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.autorunAsync)
1.  [function <span class="apidocSignatureSpan">mobx.</span>computed (arg1, arg2, arg3)](#apidoc.element.mobx.computed)
1.  [function <span class="apidocSignatureSpan">mobx.</span>createTransformer (transformer, onCleanup)](#apidoc.element.mobx.createTransformer)
1.  [function <span class="apidocSignatureSpan">mobx.</span>expr (expr, scope)](#apidoc.element.mobx.expr)
1.  [function <span class="apidocSignatureSpan">mobx.</span>extendObservable (target)](#apidoc.element.mobx.extendObservable)
1.  [function <span class="apidocSignatureSpan">mobx.</span>extendShallowObservable (target)](#apidoc.element.mobx.extendShallowObservable)
1.  [function <span class="apidocSignatureSpan">mobx.</span>intercept (thing, propOrHandler, handler)](#apidoc.element.mobx.intercept)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isAction (thing)](#apidoc.element.mobx.isAction)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isArrayLike (x)](#apidoc.element.mobx.isArrayLike)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isBoxedObservable (x)](#apidoc.element.mobx.isBoxedObservable)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isComputed (value, property)](#apidoc.element.mobx.isComputed)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isModifierDescriptor (thing)](#apidoc.element.mobx.isModifierDescriptor)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isObservable (value, property)](#apidoc.element.mobx.isObservable)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isObservableArray (thing)](#apidoc.element.mobx.isObservableArray)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isObservableMap (x)](#apidoc.element.mobx.isObservableMap)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isObservableObject (thing)](#apidoc.element.mobx.isObservableObject)
1.  [function <span class="apidocSignatureSpan">mobx.</span>isStrictModeEnabled ()](#apidoc.element.mobx.isStrictModeEnabled)
1.  [function <span class="apidocSignatureSpan">mobx.</span>map (initialValues)](#apidoc.element.mobx.map)
1.  [function <span class="apidocSignatureSpan">mobx.</span>observable (v)](#apidoc.element.mobx.observable)
1.  [function <span class="apidocSignatureSpan">mobx.</span>observe (thing, propOrCb, cbOrFire, fireImmediately)](#apidoc.element.mobx.observe)
1.  [function <span class="apidocSignatureSpan">mobx.</span>reaction (expression, effect, arg3)](#apidoc.element.mobx.reaction)
1.  [function <span class="apidocSignatureSpan">mobx.</span>runInAction (arg1, arg2, arg3)](#apidoc.element.mobx.runInAction)
1.  [function <span class="apidocSignatureSpan">mobx.</span>spy (listener)](#apidoc.element.mobx.spy)
1.  [function <span class="apidocSignatureSpan">mobx.</span>toJS (source, detectCycles, __alreadySeen)](#apidoc.element.mobx.toJS)
1.  [function <span class="apidocSignatureSpan">mobx.</span>transaction (action, thisArg)](#apidoc.element.mobx.transaction)
1.  [function <span class="apidocSignatureSpan">mobx.</span>untracked (action)](#apidoc.element.mobx.untracked)
1.  [function <span class="apidocSignatureSpan">mobx.</span>useStrict (strict)](#apidoc.element.mobx.useStrict)
1.  [function <span class="apidocSignatureSpan">mobx.</span>when (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.when)
1.  [function <span class="apidocSignatureSpan">mobx.</span>whyRun (thing, prop)](#apidoc.element.mobx.whyRun)
1.  object <span class="apidocSignatureSpan">mobx.</span>Atom.prototype
1.  object <span class="apidocSignatureSpan">mobx.</span>BaseAtom.prototype
1.  object <span class="apidocSignatureSpan">mobx.</span>IDerivationState
1.  object <span class="apidocSignatureSpan">mobx.</span>IObservableFactories.prototype
1.  object <span class="apidocSignatureSpan">mobx.</span>ObservableMap.prototype
1.  object <span class="apidocSignatureSpan">mobx.</span>Reaction.prototype
1.  object <span class="apidocSignatureSpan">mobx.</span>default
1.  object <span class="apidocSignatureSpan">mobx.</span>extras
1.  object <span class="apidocSignatureSpan">mobx.</span>mobx_umd

#### [module mobx.Atom](#apidoc.module.mobx.Atom)
1.  [function <span class="apidocSignatureSpan">mobx.</span>Atom (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.Atom.Atom)

#### [module mobx.Atom.prototype](#apidoc.module.mobx.Atom.prototype)
1.  [function <span class="apidocSignatureSpan">mobx.Atom.prototype.</span>constructor (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.Atom.prototype.constructor)
1.  [function <span class="apidocSignatureSpan">mobx.Atom.prototype.</span>onBecomeUnobserved ()](#apidoc.element.mobx.Atom.prototype.onBecomeUnobserved)
1.  [function <span class="apidocSignatureSpan">mobx.Atom.prototype.</span>reportObserved ()](#apidoc.element.mobx.Atom.prototype.reportObserved)

#### [module mobx.BaseAtom](#apidoc.module.mobx.BaseAtom)
1.  [function <span class="apidocSignatureSpan">mobx.</span>BaseAtom (name)](#apidoc.element.mobx.BaseAtom.BaseAtom)

#### [module mobx.BaseAtom.prototype](#apidoc.module.mobx.BaseAtom.prototype)
1.  boolean <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>isMobXAtom
1.  [function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>onBecomeUnobserved ()](#apidoc.element.mobx.BaseAtom.prototype.onBecomeUnobserved)
1.  [function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>reportChanged ()](#apidoc.element.mobx.BaseAtom.prototype.reportChanged)
1.  [function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>reportObserved ()](#apidoc.element.mobx.BaseAtom.prototype.reportObserved)
1.  [function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>toString ()](#apidoc.element.mobx.BaseAtom.prototype.toString)

#### [module mobx.IObservableFactories](#apidoc.module.mobx.IObservableFactories)
1.  [function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories ()](#apidoc.element.mobx.IObservableFactories.IObservableFactories)

#### [module mobx.IObservableFactories.prototype](#apidoc.module.mobx.IObservableFactories.prototype)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>array (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.array)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>box (value, name)](#apidoc.element.mobx.IObservableFactories.prototype.box)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>deep ()](#apidoc.element.mobx.IObservableFactories.prototype.deep)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>map (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.map)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>object (props, name)](#apidoc.element.mobx.IObservableFactories.prototype.object)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>ref ()](#apidoc.element.mobx.IObservableFactories.prototype.ref)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallow ()](#apidoc.element.mobx.IObservableFactories.prototype.shallow)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowArray (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowArray)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowBox (value, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowBox)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowMap (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowMap)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowObject (props, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowObject)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>struct ()](#apidoc.element.mobx.IObservableFactories.prototype.struct)

#### [module mobx.IObservableFactories.prototype.deep](#apidoc.module.mobx.IObservableFactories.prototype.deep)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>deep ()](#apidoc.element.mobx.IObservableFactories.prototype.deep.deep)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.deep.</span>struct ()](#apidoc.element.mobx.IObservableFactories.prototype.deep.struct)

#### [module mobx.IObservableFactories.prototype.ref](#apidoc.module.mobx.IObservableFactories.prototype.ref)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>ref ()](#apidoc.element.mobx.IObservableFactories.prototype.ref.ref)
1.  [function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.ref.</span>struct ()](#apidoc.element.mobx.IObservableFactories.prototype.ref.struct)

#### [module mobx.ObservableMap](#apidoc.module.mobx.ObservableMap)
1.  [function <span class="apidocSignatureSpan">mobx.</span>ObservableMap (initialData, enhancer, name)](#apidoc.element.mobx.ObservableMap.ObservableMap)

#### [module mobx.ObservableMap.prototype](#apidoc.module.mobx.ObservableMap.prototype)
1.  boolean <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>isMobXObservableMap
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_addValue (name, newValue)](#apidoc.element.mobx.ObservableMap.prototype._addValue)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_has (key)](#apidoc.element.mobx.ObservableMap.prototype._has)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_updateHasMapEntry (key, value)](#apidoc.element.mobx.ObservableMap.prototype._updateHasMapEntry)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_updateValue (name, newValue)](#apidoc.element.mobx.ObservableMap.prototype._updateValue)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>assertValidKey (key)](#apidoc.element.mobx.ObservableMap.prototype.assertValidKey)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>clear ()](#apidoc.element.mobx.ObservableMap.prototype.clear)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>delete (key)](#apidoc.element.mobx.ObservableMap.prototype.delete)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>entries ()](#apidoc.element.mobx.ObservableMap.prototype.entries)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>forEach (callback, thisArg)](#apidoc.element.mobx.ObservableMap.prototype.forEach)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>get (key)](#apidoc.element.mobx.ObservableMap.prototype.get)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>has (key)](#apidoc.element.mobx.ObservableMap.prototype.has)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>intercept (handler)](#apidoc.element.mobx.ObservableMap.prototype.intercept)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>isValidKey (key)](#apidoc.element.mobx.ObservableMap.prototype.isValidKey)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>keys ()](#apidoc.element.mobx.ObservableMap.prototype.keys)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>merge (other)](#apidoc.element.mobx.ObservableMap.prototype.merge)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>observe (listener, fireImmediately)](#apidoc.element.mobx.ObservableMap.prototype.observe)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>replace (values)](#apidoc.element.mobx.ObservableMap.prototype.replace)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>set (key, value)](#apidoc.element.mobx.ObservableMap.prototype.set)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>toJS ()](#apidoc.element.mobx.ObservableMap.prototype.toJS)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>toJSON ()](#apidoc.element.mobx.ObservableMap.prototype.toJSON)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>toString ()](#apidoc.element.mobx.ObservableMap.prototype.toString)
1.  [function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>values ()](#apidoc.element.mobx.ObservableMap.prototype.values)

#### [module mobx.Reaction](#apidoc.module.mobx.Reaction)
1.  [function <span class="apidocSignatureSpan">mobx.</span>Reaction (name, onInvalidate)](#apidoc.element.mobx.Reaction.Reaction)

#### [module mobx.Reaction.prototype](#apidoc.module.mobx.Reaction.prototype)
1.  boolean <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>isMobXReaction
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>dispose ()](#apidoc.element.mobx.Reaction.prototype.dispose)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>getDisposer ()](#apidoc.element.mobx.Reaction.prototype.getDisposer)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>isScheduled ()](#apidoc.element.mobx.Reaction.prototype.isScheduled)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>onBecomeStale ()](#apidoc.element.mobx.Reaction.prototype.onBecomeStale)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>reportExceptionInDerivation (error)](#apidoc.element.mobx.Reaction.prototype.reportExceptionInDerivation)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>runReaction ()](#apidoc.element.mobx.Reaction.prototype.runReaction)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>schedule ()](#apidoc.element.mobx.Reaction.prototype.schedule)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>toString ()](#apidoc.element.mobx.Reaction.prototype.toString)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>track (fn)](#apidoc.element.mobx.Reaction.prototype.track)
1.  [function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>whyRun ()](#apidoc.element.mobx.Reaction.prototype.whyRun)

#### [module mobx.action](#apidoc.module.mobx.action)
1.  [function <span class="apidocSignatureSpan">mobx.</span>action (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.action.action)
1.  [function <span class="apidocSignatureSpan">mobx.action.</span>bound (arg1, arg2, arg3)](#apidoc.element.mobx.action.bound)

#### [module mobx.computed](#apidoc.module.mobx.computed)
1.  [function <span class="apidocSignatureSpan">mobx.</span>computed (arg1, arg2, arg3)](#apidoc.element.mobx.computed.computed)
1.  [function <span class="apidocSignatureSpan">mobx.computed.</span>struct (target, key, descriptor, customArgs, argLen)](#apidoc.element.mobx.computed.struct)

#### [module mobx.extras](#apidoc.module.mobx.extras)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>allowStateChanges (allowStateChanges, func)](#apidoc.element.mobx.extras.allowStateChanges)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>deepEqual (a, b)](#apidoc.element.mobx.extras.deepEqual)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>getAdministration (thing, property)](#apidoc.element.mobx.extras.getAdministration)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>getAtom (thing, property)](#apidoc.element.mobx.extras.getAtom)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>getDebugName (thing, property)](#apidoc.element.mobx.extras.getDebugName)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>getDependencyTree (thing, property)](#apidoc.element.mobx.extras.getDependencyTree)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>getGlobalState ()](#apidoc.element.mobx.extras.getGlobalState)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>getObserverTree (thing, property)](#apidoc.element.mobx.extras.getObserverTree)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>isComputingDerivation ()](#apidoc.element.mobx.extras.isComputingDerivation)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>isSpyEnabled ()](#apidoc.element.mobx.extras.isSpyEnabled)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>onReactionError (handler)](#apidoc.element.mobx.extras.onReactionError)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>resetGlobalState ()](#apidoc.element.mobx.extras.resetGlobalState)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>setReactionScheduler (fn)](#apidoc.element.mobx.extras.setReactionScheduler)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>shareGlobalState ()](#apidoc.element.mobx.extras.shareGlobalState)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>spyReport (event)](#apidoc.element.mobx.extras.spyReport)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>spyReportEnd (change)](#apidoc.element.mobx.extras.spyReportEnd)
1.  [function <span class="apidocSignatureSpan">mobx.extras.</span>spyReportStart (event)](#apidoc.element.mobx.extras.spyReportStart)

#### [module mobx.mobx_umd](#apidoc.module.mobx.mobx_umd)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>Atom (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.mobx_umd.Atom)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>BaseAtom (name)](#apidoc.element.mobx.mobx_umd.BaseAtom)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>IObservableFactories ()](#apidoc.element.mobx.mobx_umd.IObservableFactories)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>ObservableMap (initialData, enhancer, name)](#apidoc.element.mobx.mobx_umd.ObservableMap)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>Reaction (name, onInvalidate)](#apidoc.element.mobx.mobx_umd.Reaction)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>action (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.mobx_umd.action)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asFlat (value)](#apidoc.element.mobx.mobx_umd.asFlat)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asMap (data)](#apidoc.element.mobx.mobx_umd.asMap)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asReference (value)](#apidoc.element.mobx.mobx_umd.asReference)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asStructure (value)](#apidoc.element.mobx.mobx_umd.asStructure)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>autorun (arg1, arg2, arg3)](#apidoc.element.mobx.mobx_umd.autorun)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>autorunAsync (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.mobx_umd.autorunAsync)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>computed (arg1, arg2, arg3)](#apidoc.element.mobx.mobx_umd.computed)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>createTransformer (transformer, onCleanup)](#apidoc.element.mobx.mobx_umd.createTransformer)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>expr (expr, scope)](#apidoc.element.mobx.mobx_umd.expr)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>extendObservable (target)](#apidoc.element.mobx.mobx_umd.extendObservable)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>extendShallowObservable (target)](#apidoc.element.mobx.mobx_umd.extendShallowObservable)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>intercept (thing, propOrHandler, handler)](#apidoc.element.mobx.mobx_umd.intercept)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isAction (thing)](#apidoc.element.mobx.mobx_umd.isAction)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isArrayLike (x)](#apidoc.element.mobx.mobx_umd.isArrayLike)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isBoxedObservable (x)](#apidoc.element.mobx.mobx_umd.isBoxedObservable)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isComputed (value, property)](#apidoc.element.mobx.mobx_umd.isComputed)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isModifierDescriptor (thing)](#apidoc.element.mobx.mobx_umd.isModifierDescriptor)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservable (value, property)](#apidoc.element.mobx.mobx_umd.isObservable)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservableArray (thing)](#apidoc.element.mobx.mobx_umd.isObservableArray)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservableMap (x)](#apidoc.element.mobx.mobx_umd.isObservableMap)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservableObject (thing)](#apidoc.element.mobx.mobx_umd.isObservableObject)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isStrictModeEnabled ()](#apidoc.element.mobx.mobx_umd.isStrictModeEnabled)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>map (initialValues)](#apidoc.element.mobx.mobx_umd.map)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>observable (v)](#apidoc.element.mobx.mobx_umd.observable)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>observe (thing, propOrCb, cbOrFire, fireImmediately)](#apidoc.element.mobx.mobx_umd.observe)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>reaction (expression, effect, arg3)](#apidoc.element.mobx.mobx_umd.reaction)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>runInAction (arg1, arg2, arg3)](#apidoc.element.mobx.mobx_umd.runInAction)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>spy (listener)](#apidoc.element.mobx.mobx_umd.spy)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>toJS (source, detectCycles, __alreadySeen)](#apidoc.element.mobx.mobx_umd.toJS)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>transaction (action, thisArg)](#apidoc.element.mobx.mobx_umd.transaction)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>untracked (action)](#apidoc.element.mobx.mobx_umd.untracked)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>useStrict (strict)](#apidoc.element.mobx.mobx_umd.useStrict)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>when (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.mobx_umd.when)
1.  [function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>whyRun (thing, prop)](#apidoc.element.mobx.mobx_umd.whyRun)
1.  object <span class="apidocSignatureSpan">mobx.mobx_umd.</span>IDerivationState
1.  object <span class="apidocSignatureSpan">mobx.mobx_umd.</span>default
1.  object <span class="apidocSignatureSpan">mobx.mobx_umd.</span>extras

#### [module mobx.observable](#apidoc.module.mobx.observable)
1.  [function <span class="apidocSignatureSpan">mobx.</span>observable (v)](#apidoc.element.mobx.observable.observable)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>array (initialValues, name)](#apidoc.element.mobx.observable.array)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>box (value, name)](#apidoc.element.mobx.observable.box)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>deep ()](#apidoc.element.mobx.observable.deep)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>map (initialValues, name)](#apidoc.element.mobx.observable.map)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>object (props, name)](#apidoc.element.mobx.observable.object)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>ref ()](#apidoc.element.mobx.observable.ref)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>shallow ()](#apidoc.element.mobx.observable.shallow)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>shallowArray (initialValues, name)](#apidoc.element.mobx.observable.shallowArray)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>shallowBox (value, name)](#apidoc.element.mobx.observable.shallowBox)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>shallowMap (initialValues, name)](#apidoc.element.mobx.observable.shallowMap)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>shallowObject (props, name)](#apidoc.element.mobx.observable.shallowObject)
1.  [function <span class="apidocSignatureSpan">mobx.observable.</span>struct ()](#apidoc.element.mobx.observable.struct)



# <a name="apidoc.module.mobx"></a>[module mobx](#apidoc.module.mobx)

#### <a name="apidoc.element.mobx.Atom"></a>[function <span class="apidocSignatureSpan">mobx.</span>Atom (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.Atom)
- description and source-code
```javascript
function Atom(name, onBecomeObservedHandler, onBecomeUnobservedHandler) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    if (onBecomeObservedHandler === void 0) { onBecomeObservedHandler = noop; }
    if (onBecomeUnobservedHandler === void 0) { onBecomeUnobservedHandler = noop; }
    var _this = _super.call(this, name) || this;
    _this.name = name;
    _this.onBecomeObservedHandler = onBecomeObservedHandler;
    _this.onBecomeUnobservedHandler = onBecomeUnobservedHandler;
    _this.isPendingUnobservation = false;
    _this.isBeingTracked = false;
    return _this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.BaseAtom"></a>[function <span class="apidocSignatureSpan">mobx.</span>BaseAtom (name)](#apidoc.element.mobx.BaseAtom)
- description and source-code
```javascript
function BaseAtom(name) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    this.name = name;
    this.isPendingUnobservation = true;
    this.observers = [];
    this.observersIndexes = {};
    this.diffValue = 0;
    this.lastAccessedBy = 0;
    this.lowestObserverState = IDerivationState.NOT_TRACKING;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.IObservableFactories"></a>[function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories ()](#apidoc.element.mobx.IObservableFactories)
- description and source-code
```javascript
function IObservableFactories() {
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.deep"></a>[function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories.prototype.deep ()](#apidoc.element.mobx.IObservableFactories.prototype.deep)
- description and source-code
```javascript
IObservableFactories.prototype.deep = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepEnhancer, arguments[0]);
    }
    else {
        return deepDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.ref"></a>[function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories.prototype.ref ()](#apidoc.element.mobx.IObservableFactories.prototype.ref)
- description and source-code
```javascript
IObservableFactories.prototype.ref = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(referenceEnhancer, arguments[0]);
    }
    else {
        return refDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.ObservableMap"></a>[function <span class="apidocSignatureSpan">mobx.</span>ObservableMap (initialData, enhancer, name)](#apidoc.element.mobx.ObservableMap)
- description and source-code
```javascript
function ObservableMap(initialData, enhancer, name) {
    if (enhancer === void 0) { enhancer = deepEnhancer; }
    if (name === void 0) { name = "ObservableMap@" + getNextId(); }
    this.enhancer = enhancer;
    this.name = name;
    this.$mobx = ObservableMapMarker;
    this._data = Object.create(null);
    this._hasMap = Object.create(null);
    this._keys = new ObservableArray(undefined, referenceEnhancer, this.name + ".keys()", true);
    this.interceptors = null;
    this.changeListeners = null;
    this.merge(initialData);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.Reaction"></a>[function <span class="apidocSignatureSpan">mobx.</span>Reaction (name, onInvalidate)](#apidoc.element.mobx.Reaction)
- description and source-code
```javascript
function Reaction(name, onInvalidate) {
    if (name === void 0) { name = "Reaction@" + getNextId(); }
    this.name = name;
    this.onInvalidate = onInvalidate;
    this.observing = [];
    this.newObserving = [];
    this.dependenciesState = IDerivationState.NOT_TRACKING;
    this.diffValue = 0;
    this.runId = 0;
    this.unboundDepsCount = 0;
    this.__mapid = "#" + getNextId();
    this.isDisposed = false;
    this._isScheduled = false;
    this._isTrackPending = false;
    this._isRunning = false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.action"></a>[function <span class="apidocSignatureSpan">mobx.</span>action (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.action)
- description and source-code
```javascript
function action(arg1, arg2, arg3, arg4) {
    if (arguments.length === 1 && typeof arg1 === "function")
        return createAction(arg1.name || "<unnamed action>", arg1);
    if (arguments.length === 2 && typeof arg2 === "function")
        return createAction(arg1, arg2);
    if (arguments.length === 1 && typeof arg1 === "string")
        return namedActionDecorator(arg1);
    return namedActionDecorator(arg2).apply(null, arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.asFlat"></a>[function <span class="apidocSignatureSpan">mobx.</span>asFlat (value)](#apidoc.element.mobx.asFlat)
- description and source-code
```javascript
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.asMap"></a>[function <span class="apidocSignatureSpan">mobx.</span>asMap (data)](#apidoc.element.mobx.asMap)
- description and source-code
```javascript
function asMap(data) {
    deprecated("asMap is deprecated, use observable.map or observable.shallowMap instead");
    return observable.map(data || {});
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.asReference"></a>[function <span class="apidocSignatureSpan">mobx.</span>asReference (value)](#apidoc.element.mobx.asReference)
- description and source-code
```javascript
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.asStructure"></a>[function <span class="apidocSignatureSpan">mobx.</span>asStructure (value)](#apidoc.element.mobx.asStructure)
- description and source-code
```javascript
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.autorun"></a>[function <span class="apidocSignatureSpan">mobx.</span>autorun (arg1, arg2, arg3)](#apidoc.element.mobx.autorun)
- description and source-code
```javascript
function autorun(arg1, arg2, arg3) {
    var name, view, scope;
    if (typeof arg1 === "string") {
        name = arg1;
        view = arg2;
        scope = arg3;
    }
    else {
        name = arg1.name || ("Autorun@" + getNextId());
        view = arg1;
        scope = arg2;
    }
    invariant(typeof view === "function", getMessage("m004"));
    invariant(isAction(view) === false, getMessage("m005"));
    if (scope)
        view = view.bind(scope);
    var reaction = new Reaction(name, function () {
        this.track(reactionRunner);
    });
    function reactionRunner() {
        view(reaction);
    }
    reaction.schedule();
    return reaction.getDisposer();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.autorunAsync"></a>[function <span class="apidocSignatureSpan">mobx.</span>autorunAsync (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.autorunAsync)
- description and source-code
```javascript
function autorunAsync(arg1, arg2, arg3, arg4) {
    var name, func, delay, scope;
    if (typeof arg1 === "string") {
        name = arg1;
        func = arg2;
        delay = arg3;
        scope = arg4;
    }
    else {
        name = arg1.name || ("AutorunAsync@" + getNextId());
        func = arg1;
        delay = arg2;
        scope = arg3;
    }
    invariant(isAction(func) === false, getMessage("m006"));
    if (delay === void 0)
        delay = 1;
    if (scope)
        func = func.bind(scope);
    var isScheduled = false;
    var r = new Reaction(name, function () {
        if (!isScheduled) {
            isScheduled = true;
            setTimeout(function () {
                isScheduled = false;
                if (!r.isDisposed)
                    r.track(reactionRunner);
            }, delay);
        }
    });
    function reactionRunner() { func(r); }
    r.schedule();
    return r.getDisposer();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.computed"></a>[function <span class="apidocSignatureSpan">mobx.</span>computed (arg1, arg2, arg3)](#apidoc.element.mobx.computed)
- description and source-code
```javascript
function computed(arg1, arg2, arg3) {
    if (typeof arg2 === "string") {
        return computedDecorator.apply(null, arguments);
    }
    invariant(typeof arg1 === "function", getMessage("m011"));
    invariant(arguments.length < 3, getMessage("m012"));
    var opts = typeof arg2 === "object" ? arg2 : {};
    opts.setter = typeof arg2 === "function" ? arg2 : opts.setter;
    return new ComputedValue(arg1, opts.context, opts.compareStructural || opts.struct || false, opts.name || arg1.name || "", opts
.setter);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.createTransformer"></a>[function <span class="apidocSignatureSpan">mobx.</span>createTransformer (transformer, onCleanup)](#apidoc.element.mobx.createTransformer)
- description and source-code
```javascript
function createTransformer(transformer, onCleanup) {
    invariant(typeof transformer === "function" && transformer.length < 2, "createTransformer expects a function that accepts one
 argument");
    var objectCache = {};
    var resetId = globalState.resetId;
    var Transformer = (function (_super) {
        __extends(Transformer, _super);
        function Transformer(sourceIdentifier, sourceObject) {
            var _this = _super.call(this, function () { return transformer(sourceObject); }, undefined, false, "Transformer-" +
transformer.name + "-" + sourceIdentifier, undefined) || this;
            _this.sourceIdentifier = sourceIdentifier;
            _this.sourceObject = sourceObject;
            return _this;
        }
        Transformer.prototype.onBecomeUnobserved = function () {
            var lastValue = this.value;
            _super.prototype.onBecomeUnobserved.call(this);
            delete objectCache[this.sourceIdentifier];
            if (onCleanup)
                onCleanup(lastValue, this.sourceObject);
        };
        return Transformer;
    }(ComputedValue));
    return function (object) {
        if (resetId !== globalState.resetId) {
            objectCache = {};
            resetId = globalState.resetId;
        }
        var identifier = getMemoizationId(object);
        var reactiveTransformer = objectCache[identifier];
        if (reactiveTransformer)
            return reactiveTransformer.get();
        reactiveTransformer = objectCache[identifier] = new Transformer(identifier, object);
        return reactiveTransformer.get();
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.expr"></a>[function <span class="apidocSignatureSpan">mobx.</span>expr (expr, scope)](#apidoc.element.mobx.expr)
- description and source-code
```javascript
function expr(expr, scope) {
    if (!isComputingDerivation())
        console.warn(getMessage("m013"));
    return computed(expr, { context: scope }).get();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extendObservable"></a>[function <span class="apidocSignatureSpan">mobx.</span>extendObservable (target)](#apidoc.element.mobx.extendObservable)
- description and source-code
```javascript
function extendObservable(target) {
    var properties = [];
    for (var _i = 1; _i < arguments.length; _i++) {
        properties[_i - 1] = arguments[_i];
    }
    return extendObservableHelper(target, deepEnhancer, properties);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extendShallowObservable"></a>[function <span class="apidocSignatureSpan">mobx.</span>extendShallowObservable (target)](#apidoc.element.mobx.extendShallowObservable)
- description and source-code
```javascript
function extendShallowObservable(target) {
    var properties = [];
    for (var _i = 1; _i < arguments.length; _i++) {
        properties[_i - 1] = arguments[_i];
    }
    return extendObservableHelper(target, referenceEnhancer, properties);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.intercept"></a>[function <span class="apidocSignatureSpan">mobx.</span>intercept (thing, propOrHandler, handler)](#apidoc.element.mobx.intercept)
- description and source-code
```javascript
function intercept(thing, propOrHandler, handler) {
    if (typeof handler === "function")
        return interceptProperty(thing, propOrHandler, handler);
    else
        return interceptInterceptable(thing, propOrHandler);
}
```
- example usage
```shell
...
if (typeof handler === "function")
    return interceptProperty(thing, propOrHandler, handler);
else
    return interceptInterceptable(thing, propOrHandler);
}
exports.intercept = intercept;
function interceptInterceptable(thing, handler) {
return getAdministration(thing).intercept(handler);
}
function interceptProperty(thing, property, handler) {
return getAdministration(thing, property).intercept(handler);
}
function isComputed(value, property) {
if (value === null || value === undefined)
    return false;
...
```

#### <a name="apidoc.element.mobx.isAction"></a>[function <span class="apidocSignatureSpan">mobx.</span>isAction (thing)](#apidoc.element.mobx.isAction)
- description and source-code
```javascript
function isAction(thing) {
    return typeof thing === "function" && thing.isMobxAction === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isArrayLike"></a>[function <span class="apidocSignatureSpan">mobx.</span>isArrayLike (x)](#apidoc.element.mobx.isArrayLike)
- description and source-code
```javascript
function isArrayLike(x) {
    return Array.isArray(x) || isObservableArray(x);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isBoxedObservable"></a>[function <span class="apidocSignatureSpan">mobx.</span>isBoxedObservable (x)](#apidoc.element.mobx.isBoxedObservable)
- description and source-code
```javascript
isBoxedObservable = function (x) {
    return isObject(x) && x[propName] === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isComputed"></a>[function <span class="apidocSignatureSpan">mobx.</span>isComputed (value, property)](#apidoc.element.mobx.isComputed)
- description and source-code
```javascript
function isComputed(value, property) {
    if (value === null || value === undefined)
        return false;
    if (property !== undefined) {
        if (isObservableObject(value) === false)
            return false;
        var atom = getAtom(value, property);
        return isComputedValue(atom);
    }
    return isComputedValue(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isModifierDescriptor"></a>[function <span class="apidocSignatureSpan">mobx.</span>isModifierDescriptor (thing)](#apidoc.element.mobx.isModifierDescriptor)
- description and source-code
```javascript
function isModifierDescriptor(thing) {
    return typeof thing === "object" && thing !== null && thing.isMobxModifierDescriptor === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isObservable"></a>[function <span class="apidocSignatureSpan">mobx.</span>isObservable (value, property)](#apidoc.element.mobx.isObservable)
- description and source-code
```javascript
function isObservable(value, property) {
    if (value === null || value === undefined)
        return false;
    if (property !== undefined) {
        if (isObservableArray(value) || isObservableMap(value))
            throw new Error(getMessage("m019"));
        else if (isObservableObject(value)) {
            var o = value.$mobx;
            return o.values && !!o.values[property];
        }
        return false;
    }
    return isObservableObject(value) || !!value.$mobx || isAtom(value) || isReaction(value) || isComputedValue(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isObservableArray"></a>[function <span class="apidocSignatureSpan">mobx.</span>isObservableArray (thing)](#apidoc.element.mobx.isObservableArray)
- description and source-code
```javascript
function isObservableArray(thing) {
    return isObject(thing) && isObservableArrayAdministration(thing.$mobx);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isObservableMap"></a>[function <span class="apidocSignatureSpan">mobx.</span>isObservableMap (x)](#apidoc.element.mobx.isObservableMap)
- description and source-code
```javascript
isObservableMap = function (x) {
    return isObject(x) && x[propName] === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isObservableObject"></a>[function <span class="apidocSignatureSpan">mobx.</span>isObservableObject (thing)](#apidoc.element.mobx.isObservableObject)
- description and source-code
```javascript
function isObservableObject(thing) {
    if (isObject(thing)) {
        runLazyInitializers(thing);
        return isObservableObjectAdministration(thing.$mobx);
    }
    return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.isStrictModeEnabled"></a>[function <span class="apidocSignatureSpan">mobx.</span>isStrictModeEnabled ()](#apidoc.element.mobx.isStrictModeEnabled)
- description and source-code
```javascript
function isStrictModeEnabled() {
    return globalState.strictMode;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.map"></a>[function <span class="apidocSignatureSpan">mobx.</span>map (initialValues)](#apidoc.element.mobx.map)
- description and source-code
```javascript
function map(initialValues) {
    deprecated("'mobx.map' is deprecated, use 'new ObservableMap' or 'mobx.observable.map' instead");
    return observable.map(initialValues);
}
```
- example usage
```shell
...
import {observer} from 'mobx-react';

@observer
class TodoListView extends Component {
    render() {
        return <div>
            <ul>
                {this.props.todoList.todos.map(todo =>
                    <TodoView todo={todo} key={todo.id} />
                )}
            </ul>
            Tasks left: {this.props.todoList.unfinishedTodoCount}
        </div>
    }
}
...
```

#### <a name="apidoc.element.mobx.observable"></a>[function <span class="apidocSignatureSpan">mobx.</span>observable (v)](#apidoc.element.mobx.observable)
- description and source-code
```javascript
function createObservable(v) {
    if (v === void 0) { v = undefined; }
    if (typeof arguments[1] === "string")
        return deepDecorator.apply(null, arguments);
    invariant(arguments.length <= 1, getMessage("m021"));
    invariant(!isModifierDescriptor(v), getMessage("m020"));
    if (isObservable(v))
        return v;
    var res = deepEnhancer(v, undefined, undefined);
    if (res !== v)
        return res;
    return observable.box(v);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.observe"></a>[function <span class="apidocSignatureSpan">mobx.</span>observe (thing, propOrCb, cbOrFire, fireImmediately)](#apidoc.element.mobx.observe)
- description and source-code
```javascript
function observe(thing, propOrCb, cbOrFire, fireImmediately) {
    if (typeof cbOrFire === "function")
        return observeObservableProperty(thing, propOrCb, cbOrFire, fireImmediately);
    else
        return observeObservable(thing, propOrCb, cbOrFire);
}
```
- example usage
```shell
...
if (typeof cbOrFire === "function")
    return observeObservableProperty(thing, propOrCb, cbOrFire, fireImmediately);
else
    return observeObservable(thing, propOrCb, cbOrFire);
}
exports.observe = observe;
function observeObservable(thing, listener, fireImmediately) {
return getAdministration(thing).observe(listener, fireImmediately);
}
function observeObservableProperty(thing, property, listener, fireImmediately) {
return getAdministration(thing, property).observe(listener, fireImmediately);
}
function toJS(source, detectCycles, __alreadySeen) {
if (detectCycles === void 0) { detectCycles = true; }
if (__alreadySeen === void 0) { __alreadySeen = []; }
...
```

#### <a name="apidoc.element.mobx.reaction"></a>[function <span class="apidocSignatureSpan">mobx.</span>reaction (expression, effect, arg3)](#apidoc.element.mobx.reaction)
- description and source-code
```javascript
function reaction(expression, effect, arg3) {
    if (arguments.length > 3) {
        fail(getMessage("m007"));
    }
    if (isModifierDescriptor(expression)) {
        fail(getMessage("m008"));
    }
    var opts;
    if (typeof arg3 === "object") {
        opts = arg3;
    }
    else {
        opts = {};
    }
    opts.name = opts.name || expression.name || effect.name || ("Reaction@" + getNextId());
    opts.fireImmediately = arg3 === true || opts.fireImmediately === true;
    opts.delay = opts.delay || 0;
    opts.compareStructural = opts.compareStructural || opts.struct || false;
    effect = action(opts.name, opts.context ? effect.bind(opts.context) : effect);
    if (opts.context) {
        expression = expression.bind(opts.context);
    }
    var firstTime = true;
    var isScheduled = false;
    var nextValue;
    var r = new Reaction(opts.name, function () {
        if (firstTime || opts.delay < 1) {
            reactionRunner();
        }
        else if (!isScheduled) {
            isScheduled = true;
            setTimeout(function () {
                isScheduled = false;
                reactionRunner();
            }, opts.delay);
        }
    });
    function reactionRunner() {
        if (r.isDisposed)
            return;
        var changed = false;
        r.track(function () {
            var v = expression(r);
            changed = valueDidChange(opts.compareStructural, nextValue, v);
            nextValue = v;
        });
        if (firstTime && opts.fireImmediately)
            effect(nextValue, r);
        if (!firstTime && changed === true)
            effect(nextValue, r);
        if (firstTime)
            firstTime = false;
    }
    r.schedule();
    return r.getDisposer();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.runInAction"></a>[function <span class="apidocSignatureSpan">mobx.</span>runInAction (arg1, arg2, arg3)](#apidoc.element.mobx.runInAction)
- description and source-code
```javascript
function runInAction(arg1, arg2, arg3) {
    var actionName = typeof arg1 === "string" ? arg1 : arg1.name || "<unnamed action>";
    var fn = typeof arg1 === "function" ? arg1 : arg2;
    var scope = typeof arg1 === "function" ? arg2 : arg3;
    invariant(typeof fn === "function", getMessage("m002"));
    invariant(fn.length === 0, getMessage("m003"));
    invariant(typeof actionName === "string" && actionName.length > 0, "actions should have valid names, got: '" + actionName + "'");
    return executeAction(actionName, fn, scope, undefined);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.spy"></a>[function <span class="apidocSignatureSpan">mobx.</span>spy (listener)](#apidoc.element.mobx.spy)
- description and source-code
```javascript
function spy(listener) {
    globalState.spyListeners.push(listener);
    return once(function () {
        var idx = globalState.spyListeners.indexOf(listener);
        if (idx !== -1)
            globalState.spyListeners.splice(idx, 1);
    });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.toJS"></a>[function <span class="apidocSignatureSpan">mobx.</span>toJS (source, detectCycles, __alreadySeen)](#apidoc.element.mobx.toJS)
- description and source-code
```javascript
function toJS(source, detectCycles, __alreadySeen) {
    if (detectCycles === void 0) { detectCycles = true; }
    if (__alreadySeen === void 0) { __alreadySeen = []; }
    function cache(value) {
        if (detectCycles)
            __alreadySeen.push([source, value]);
        return value;
    }
    if (isObservable(source)) {
        if (detectCycles && __alreadySeen === null)
            __alreadySeen = [];
        if (detectCycles && source !== null && typeof source === "object") {
            for (var i = 0, l = __alreadySeen.length; i < l; i++)
                if (__alreadySeen[i][0] === source)
                    return __alreadySeen[i][1];
        }
        if (isObservableArray(source)) {
            var res = cache([]);
            var toAdd = source.map(function (value) { return toJS(value, detectCycles, __alreadySeen); });
            res.length = toAdd.length;
            for (var i = 0, l = toAdd.length; i < l; i++)
                res[i] = toAdd[i];
            return res;
        }
        if (isObservableObject(source)) {
            var res = cache({});
            for (var key in source)
                res[key] = toJS(source[key], detectCycles, __alreadySeen);
            return res;
        }
        if (isObservableMap(source)) {
            var res_1 = cache({});
            source.forEach(function (value, key) { return res_1[key] = toJS(value, detectCycles, __alreadySeen); });
            return res_1;
        }
        if (isObservableValue(source))
            return toJS(source.get(), detectCycles, __alreadySeen);
    }
    return source;
}
```
- example usage
```shell
...
ObservableArray.prototype.replace = function (newItems) {
    return this.$mobx.spliceWithArray(0, this.$mobx.values.length, newItems);
};
ObservableArray.prototype.toJS = function () {
    return this.slice();
};
ObservableArray.prototype.toJSON = function () {
    return this.toJS();
};
ObservableArray.prototype.peek = function () {
    return this.$mobx.values;
};
ObservableArray.prototype.find = function (predicate, thisArg, fromIndex) {
    if (fromIndex === void 0) { fromIndex = 0; }
    this.$mobx.atom.reportObserved();
...
```

#### <a name="apidoc.element.mobx.transaction"></a>[function <span class="apidocSignatureSpan">mobx.</span>transaction (action, thisArg)](#apidoc.element.mobx.transaction)
- description and source-code
```javascript
function transaction(action, thisArg) {
    if (thisArg === void 0) { thisArg = undefined; }
    deprecated(getMessage("m023"));
    return runInTransaction.apply(undefined, arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.untracked"></a>[function <span class="apidocSignatureSpan">mobx.</span>untracked (action)](#apidoc.element.mobx.untracked)
- description and source-code
```javascript
function untracked(action) {
    var prev = untrackedStart();
    var res = action();
    untrackedEnd(prev);
    return res;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.useStrict"></a>[function <span class="apidocSignatureSpan">mobx.</span>useStrict (strict)](#apidoc.element.mobx.useStrict)
- description and source-code
```javascript
function useStrict(strict) {
    invariant(globalState.trackingDerivation === null, getMessage("m028"));
    globalState.strictMode = strict;
    globalState.allowStateChanges = !strict;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.when"></a>[function <span class="apidocSignatureSpan">mobx.</span>when (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.when)
- description and source-code
```javascript
function when(arg1, arg2, arg3, arg4) {
    var name, predicate, effect, scope;
    if (typeof arg1 === "string") {
        name = arg1;
        predicate = arg2;
        effect = arg3;
        scope = arg4;
    }
    else {
        name = ("When@" + getNextId());
        predicate = arg1;
        effect = arg2;
        scope = arg3;
    }
    var disposer = autorun(name, function (r) {
        if (predicate.call(scope)) {
            r.dispose();
            var prevUntracked = untrackedStart();
            effect.call(scope);
            untrackedEnd(prevUntracked);
        }
    });
    return disposer;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.whyRun"></a>[function <span class="apidocSignatureSpan">mobx.</span>whyRun (thing, prop)](#apidoc.element.mobx.whyRun)
- description and source-code
```javascript
function whyRun(thing, prop) {
    switch (arguments.length) {
        case 0:
            thing = globalState.trackingDerivation;
            if (!thing)
                return log(getMessage("m024"));
            break;
        case 2:
            thing = getAtom(thing, prop);
            break;
    }
    thing = getAtom(thing);
    if (isComputedValue(thing))
        return log(thing.whyRun());
    else if (isReaction(thing))
        return log(thing.whyRun());
    return fail(getMessage("m025"));
}
```
- example usage
```shell
...
        break;
    case 2:
        thing = getAtom(thing, prop);
        break;
}
thing = getAtom(thing);
if (isComputedValue(thing))
    return log(thing.whyRun());
else if (isReaction(thing))
    return log(thing.whyRun());
return fail(getMessage("m025"));
}
exports.whyRun = whyRun;
function createAction(actionName, fn) {
invariant(typeof fn === "function", getMessage("m026"));
...
```



# <a name="apidoc.module.mobx.Atom"></a>[module mobx.Atom](#apidoc.module.mobx.Atom)

#### <a name="apidoc.element.mobx.Atom.Atom"></a>[function <span class="apidocSignatureSpan">mobx.</span>Atom (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.Atom.Atom)
- description and source-code
```javascript
function Atom(name, onBecomeObservedHandler, onBecomeUnobservedHandler) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    if (onBecomeObservedHandler === void 0) { onBecomeObservedHandler = noop; }
    if (onBecomeUnobservedHandler === void 0) { onBecomeUnobservedHandler = noop; }
    var _this = _super.call(this, name) || this;
    _this.name = name;
    _this.onBecomeObservedHandler = onBecomeObservedHandler;
    _this.onBecomeUnobservedHandler = onBecomeUnobservedHandler;
    _this.isPendingUnobservation = false;
    _this.isBeingTracked = false;
    return _this;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.Atom.prototype"></a>[module mobx.Atom.prototype](#apidoc.module.mobx.Atom.prototype)

#### <a name="apidoc.element.mobx.Atom.prototype.constructor"></a>[function <span class="apidocSignatureSpan">mobx.Atom.prototype.</span>constructor (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.Atom.prototype.constructor)
- description and source-code
```javascript
function Atom(name, onBecomeObservedHandler, onBecomeUnobservedHandler) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    if (onBecomeObservedHandler === void 0) { onBecomeObservedHandler = noop; }
    if (onBecomeUnobservedHandler === void 0) { onBecomeUnobservedHandler = noop; }
    var _this = _super.call(this, name) || this;
    _this.name = name;
    _this.onBecomeObservedHandler = onBecomeObservedHandler;
    _this.onBecomeUnobservedHandler = onBecomeUnobservedHandler;
    _this.isPendingUnobservation = false;
    _this.isBeingTracked = false;
    return _this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.Atom.prototype.onBecomeUnobserved"></a>[function <span class="apidocSignatureSpan">mobx.Atom.prototype.</span>onBecomeUnobserved ()](#apidoc.element.mobx.Atom.prototype.onBecomeUnobserved)
- description and source-code
```javascript
onBecomeUnobserved = function () {
    this.isBeingTracked = false;
    this.onBecomeUnobservedHandler();
}
```
- example usage
```shell
...
if (--globalState.inBatch === 0) {
    runReactions();
    var list = globalState.pendingUnobservations;
    for (var i = 0; i < list.length; i++) {
        var observable_1 = list[i];
        observable_1.isPendingUnobservation = false;
        if (observable_1.observers.length === 0) {
            observable_1.onBecomeUnobserved();
        }
    }
    globalState.pendingUnobservations = [];
}
}
function reportObserved(observable) {
var derivation = globalState.trackingDerivation;
...
```

#### <a name="apidoc.element.mobx.Atom.prototype.reportObserved"></a>[function <span class="apidocSignatureSpan">mobx.Atom.prototype.</span>reportObserved ()](#apidoc.element.mobx.Atom.prototype.reportObserved)
- description and source-code
```javascript
reportObserved = function () {
    startBatch();
    _super.prototype.reportObserved.call(this);
    if (!this.isBeingTracked) {
        this.isBeingTracked = true;
        this.onBecomeObservedHandler();
    }
    endBatch();
    return !!globalState.trackingDerivation;
}
```
- example usage
```shell
...
            removed: [],
            removedCount: 0
        });
    }
    return registerListener(this, listener);
};
ObservableArrayAdministration.prototype.getArrayLength = function () {
    this.atom.reportObserved();
    return this.values.length;
};
ObservableArrayAdministration.prototype.setArrayLength = function (newLength) {
    if (typeof newLength !== "number" || newLength < 0)
        throw new Error("[mobx.array] Out of range: " + newLength);
    var currentLength = this.values.length;
    if (newLength === currentLength)
...
```



# <a name="apidoc.module.mobx.BaseAtom"></a>[module mobx.BaseAtom](#apidoc.module.mobx.BaseAtom)

#### <a name="apidoc.element.mobx.BaseAtom.BaseAtom"></a>[function <span class="apidocSignatureSpan">mobx.</span>BaseAtom (name)](#apidoc.element.mobx.BaseAtom.BaseAtom)
- description and source-code
```javascript
function BaseAtom(name) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    this.name = name;
    this.isPendingUnobservation = true;
    this.observers = [];
    this.observersIndexes = {};
    this.diffValue = 0;
    this.lastAccessedBy = 0;
    this.lowestObserverState = IDerivationState.NOT_TRACKING;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.BaseAtom.prototype"></a>[module mobx.BaseAtom.prototype](#apidoc.module.mobx.BaseAtom.prototype)

#### <a name="apidoc.element.mobx.BaseAtom.prototype.onBecomeUnobserved"></a>[function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>onBecomeUnobserved ()](#apidoc.element.mobx.BaseAtom.prototype.onBecomeUnobserved)
- description and source-code
```javascript
onBecomeUnobserved = function () {
}
```
- example usage
```shell
...
if (--globalState.inBatch === 0) {
    runReactions();
    var list = globalState.pendingUnobservations;
    for (var i = 0; i < list.length; i++) {
        var observable_1 = list[i];
        observable_1.isPendingUnobservation = false;
        if (observable_1.observers.length === 0) {
            observable_1.onBecomeUnobserved();
        }
    }
    globalState.pendingUnobservations = [];
}
}
function reportObserved(observable) {
var derivation = globalState.trackingDerivation;
...
```

#### <a name="apidoc.element.mobx.BaseAtom.prototype.reportChanged"></a>[function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>reportChanged ()](#apidoc.element.mobx.BaseAtom.prototype.reportChanged)
- description and source-code
```javascript
reportChanged = function () {
    startBatch();
    propagateChanged(this);
    endBatch();
}
```
- example usage
```shell
...
    var change = notify || notifySpy ? {
        object: this.array,
        type: "update",
        index: index, newValue: newValue, oldValue: oldValue
    } : null;
    if (notifySpy)
        spyReportStart(change);
    this.atom.reportChanged();
    if (notify)
        notifyListeners(this, change);
    if (notifySpy)
        spyReportEnd();
};
ObservableArrayAdministration.prototype.notifyArraySplice = function (index, added, removed) {
    var notifySpy = !this.owned && isSpyEnabled();
...
```

#### <a name="apidoc.element.mobx.BaseAtom.prototype.reportObserved"></a>[function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>reportObserved ()](#apidoc.element.mobx.BaseAtom.prototype.reportObserved)
- description and source-code
```javascript
reportObserved = function () {
    reportObserved(this);
}
```
- example usage
```shell
...
            removed: [],
            removedCount: 0
        });
    }
    return registerListener(this, listener);
};
ObservableArrayAdministration.prototype.getArrayLength = function () {
    this.atom.reportObserved();
    return this.values.length;
};
ObservableArrayAdministration.prototype.setArrayLength = function (newLength) {
    if (typeof newLength !== "number" || newLength < 0)
        throw new Error("[mobx.array] Out of range: " + newLength);
    var currentLength = this.values.length;
    if (newLength === currentLength)
...
```

#### <a name="apidoc.element.mobx.BaseAtom.prototype.toString"></a>[function <span class="apidocSignatureSpan">mobx.BaseAtom.prototype.</span>toString ()](#apidoc.element.mobx.BaseAtom.prototype.toString)
- description and source-code
```javascript
toString = function () {
    return this.name;
}
```
- example usage
```shell
...
        prevValue = newValue;
    });
};
ComputedValue.prototype.toJSON = function () {
    return this.get();
};
ComputedValue.prototype.toString = function () {
    return this.name + "[" + this.derivation.toString() + "]";
};
ComputedValue.prototype.valueOf = function () {
    return toPrimitive(this.get());
};
;
ComputedValue.prototype.whyRun = function () {
    var isTracking = Boolean(globalState.trackingDerivation);
...
```



# <a name="apidoc.module.mobx.IObservableFactories"></a>[module mobx.IObservableFactories](#apidoc.module.mobx.IObservableFactories)

#### <a name="apidoc.element.mobx.IObservableFactories.IObservableFactories"></a>[function <span class="apidocSignatureSpan">mobx.</span>IObservableFactories ()](#apidoc.element.mobx.IObservableFactories.IObservableFactories)
- description and source-code
```javascript
function IObservableFactories() {
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.IObservableFactories.prototype"></a>[module mobx.IObservableFactories.prototype](#apidoc.module.mobx.IObservableFactories.prototype)

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.array"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>array (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.array)
- description and source-code
```javascript
array = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("array");
    return new ObservableArray(initialValues, deepEnhancer, name);
}
```
- example usage
```shell
...
}
function deepEnhancer(v, _, name) {
    if (isModifierDescriptor(v))
        fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection
, not when modifying it");
    if (isObservable(v))
        return v;
    if (Array.isArray(v))
        return observable.array(v, name);
    if (isPlainObject(v))
        return observable.object(v, name);
    if (isES6Map(v))
        return observable.map(v, name);
    return v;
}
function shallowEnhancer(v, _, name) {
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.box"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>box (value, name)](#apidoc.element.mobx.IObservableFactories.prototype.box)
- description and source-code
```javascript
box = function (value, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("box");
    return new ObservableValue(value, deepEnhancer, name);
}
```
- example usage
```shell
...
invariant(arguments.length <= 1, getMessage("m021"));
invariant(!isModifierDescriptor(v), getMessage("m020"));
if (isObservable(v))
    return v;
var res = deepEnhancer(v, undefined, undefined);
if (res !== v)
    return res;
return observable.box(v);
}
var IObservableFactories = (function () {
function IObservableFactories() {
}
IObservableFactories.prototype.box = function (value, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("box");
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.deep"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>deep ()](#apidoc.element.mobx.IObservableFactories.prototype.deep)
- description and source-code
```javascript
deep = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepEnhancer, arguments[0]);
    }
    else {
        return deepDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.map"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>map (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.map)
- description and source-code
```javascript
map = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("map");
    return new ObservableMap(initialValues, deepEnhancer, name);
}
```
- example usage
```shell
...
import {observer} from 'mobx-react';

@observer
class TodoListView extends Component {
    render() {
        return <div>
            <ul>
                {this.props.todoList.todos.map(todo =>
                    <TodoView todo={todo} key={todo.id} />
                )}
            </ul>
            Tasks left: {this.props.todoList.unfinishedTodoCount}
        </div>
    }
}
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.object"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>object (props, name)](#apidoc.element.mobx.IObservableFactories.prototype.object)
- description and source-code
```javascript
object = function (props, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("object");
    var res = {};
    asObservableObject(res, name);
    extendObservable(res, props);
    return res;
}
```
- example usage
```shell
...
if (isModifierDescriptor(v))
    fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection, not
 when modifying it");
if (isObservable(v))
    return v;
if (Array.isArray(v))
    return observable.array(v, name);
if (isPlainObject(v))
    return observable.object(v, name);
if (isES6Map(v))
    return observable.map(v, name);
return v;
}
function shallowEnhancer(v, _, name) {
if (isModifierDescriptor(v))
    fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection, not
 when modifying it");
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.ref"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>ref ()](#apidoc.element.mobx.IObservableFactories.prototype.ref)
- description and source-code
```javascript
ref = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(referenceEnhancer, arguments[0]);
    }
    else {
        return refDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
    for (var i = 0, l = listeners.length; i < l; i++) {
        listeners[i](change);
    }
    untrackedEnd(prevU);
}
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.shallow"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallow ()](#apidoc.element.mobx.IObservableFactories.prototype.shallow)
- description and source-code
```javascript
shallow = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(shallowEnhancer, arguments[0]);
    }
    else {
        return shallowDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
function asMap(data) {
    deprecated("asMap is deprecated, use observable.map or observable.shallowMap instead");
    return observable.map(data || {});
}
exports.asMap = asMap;
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.shallowArray"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowArray (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowArray)
- description and source-code
```javascript
shallowArray = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowArray");
    return new ObservableArray(initialValues, referenceEnhancer, name);
}
```
- example usage
```shell
...
    if (isModifierDescriptor(v))
        fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection
, not when modifying it");
    if (v === undefined || v === null)
        return v;
    if (isObservableObject(v) || isObservableArray(v) || isObservableMap(v))
        return v;
    if (Array.isArray(v))
        return observable.shallowArray(v, name);
    if (isPlainObject(v))
        return observable.shallowObject(v, name);
    if (isES6Map(v))
        return observable.shallowMap(v, name);
    return fail("The shallow modifier / decorator can only used in combination with arrays, objects and maps");
}
function referenceEnhancer(newValue) {
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.shallowBox"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowBox (value, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowBox)
- description and source-code
```javascript
shallowBox = function (value, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowBox");
    return new ObservableValue(value, referenceEnhancer, name);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.shallowMap"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowMap (initialValues, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowMap)
- description and source-code
```javascript
shallowMap = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowMap");
    return new ObservableMap(initialValues, referenceEnhancer, name);
}
```
- example usage
```shell
...
if (isObservableObject(v) || isObservableArray(v) || isObservableMap(v))
    return v;
if (Array.isArray(v))
    return observable.shallowArray(v, name);
if (isPlainObject(v))
    return observable.shallowObject(v, name);
if (isES6Map(v))
    return observable.shallowMap(v, name);
return fail("The shallow modifier / decorator can only used in combination with arrays, objects and maps");
}
function referenceEnhancer(newValue) {
return newValue;
}
function deepStructEnhancer(v, oldValue, name) {
if (deepEqual(v, oldValue))
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.shallowObject"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>shallowObject (props, name)](#apidoc.element.mobx.IObservableFactories.prototype.shallowObject)
- description and source-code
```javascript
shallowObject = function (props, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowObject");
    var res = {};
    asObservableObject(res, name);
    extendShallowObservable(res, props);
    return res;
}
```
- example usage
```shell
...
    if (v === undefined || v === null)
        return v;
    if (isObservableObject(v) || isObservableArray(v) || isObservableMap(v))
        return v;
    if (Array.isArray(v))
        return observable.shallowArray(v, name);
    if (isPlainObject(v))
        return observable.shallowObject(v, name);
    if (isES6Map(v))
        return observable.shallowMap(v, name);
    return fail("The shallow modifier / decorator can only used in combination with arrays, objects and maps");
}
function referenceEnhancer(newValue) {
    return newValue;
}
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.struct"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>struct ()](#apidoc.element.mobx.IObservableFactories.prototype.struct)
- description and source-code
```javascript
struct = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepStructEnhancer, arguments[0]);
    }
    else {
        return deepStructDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
...
```



# <a name="apidoc.module.mobx.IObservableFactories.prototype.deep"></a>[module mobx.IObservableFactories.prototype.deep](#apidoc.module.mobx.IObservableFactories.prototype.deep)

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.deep.deep"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>deep ()](#apidoc.element.mobx.IObservableFactories.prototype.deep.deep)
- description and source-code
```javascript
deep = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepEnhancer, arguments[0]);
    }
    else {
        return deepDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.deep.struct"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.deep.</span>struct ()](#apidoc.element.mobx.IObservableFactories.prototype.deep.struct)
- description and source-code
```javascript
struct = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepStructEnhancer, arguments[0]);
    }
    else {
        return deepStructDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
...
```



# <a name="apidoc.module.mobx.IObservableFactories.prototype.ref"></a>[module mobx.IObservableFactories.prototype.ref](#apidoc.module.mobx.IObservableFactories.prototype.ref)

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.ref.ref"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.</span>ref ()](#apidoc.element.mobx.IObservableFactories.prototype.ref.ref)
- description and source-code
```javascript
ref = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(referenceEnhancer, arguments[0]);
    }
    else {
        return refDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
    for (var i = 0, l = listeners.length; i < l; i++) {
        listeners[i](change);
    }
    untrackedEnd(prevU);
}
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
...
```

#### <a name="apidoc.element.mobx.IObservableFactories.prototype.ref.struct"></a>[function <span class="apidocSignatureSpan">mobx.IObservableFactories.prototype.ref.</span>struct ()](#apidoc.element.mobx.IObservableFactories.prototype.ref.struct)
- description and source-code
```javascript
struct = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(refStructEnhancer, arguments[0]);
    }
    else {
        return refStructDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
...
```



# <a name="apidoc.module.mobx.ObservableMap"></a>[module mobx.ObservableMap](#apidoc.module.mobx.ObservableMap)

#### <a name="apidoc.element.mobx.ObservableMap.ObservableMap"></a>[function <span class="apidocSignatureSpan">mobx.</span>ObservableMap (initialData, enhancer, name)](#apidoc.element.mobx.ObservableMap.ObservableMap)
- description and source-code
```javascript
function ObservableMap(initialData, enhancer, name) {
    if (enhancer === void 0) { enhancer = deepEnhancer; }
    if (name === void 0) { name = "ObservableMap@" + getNextId(); }
    this.enhancer = enhancer;
    this.name = name;
    this.$mobx = ObservableMapMarker;
    this._data = Object.create(null);
    this._hasMap = Object.create(null);
    this._keys = new ObservableArray(undefined, referenceEnhancer, this.name + ".keys()", true);
    this.interceptors = null;
    this.changeListeners = null;
    this.merge(initialData);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.ObservableMap.prototype"></a>[module mobx.ObservableMap.prototype](#apidoc.module.mobx.ObservableMap.prototype)

#### <a name="apidoc.element.mobx.ObservableMap.prototype._addValue"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_addValue (name, newValue)](#apidoc.element.mobx.ObservableMap.prototype._addValue)
- description and source-code
```javascript
_addValue = function (name, newValue) {
    var _this = this;
    runInTransaction(function () {
        var observable = _this._data[name] = new ObservableValue(newValue, _this.enhancer, _this.name + "." + name, false);
        newValue = observable.value;
        _this._updateHasMapEntry(name, true);
        _this._keys.push(name);
    });
    var notifySpy = isSpyEnabled();
    var notify = hasListeners(this);
    var change = notify || notifySpy ? {
        type: "add",
        object: this,
        name: name, newValue: newValue
    } : null;
    if (notifySpy)
        spyReportStart(change);
    if (notify)
        notifyListeners(this, change);
    if (notifySpy)
        spyReportEnd();
}
```
- example usage
```shell
...
            return this;
        value = change.newValue;
    }
    if (hasKey) {
        this._updateValue(key, value);
    }
    else {
        this._addValue(key, value);
    }
    return this;
};
ObservableMap.prototype.delete = function (key) {
    var _this = this;
    this.assertValidKey(key);
    key = "" + key;
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype._has"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_has (key)](#apidoc.element.mobx.ObservableMap.prototype._has)
- description and source-code
```javascript
_has = function (key) {
    return typeof this._data[key] !== "undefined";
}
```
- example usage
```shell
...
    if (this._hasMap[key])
        return this._hasMap[key].get();
    return this._updateHasMapEntry(key, false).get();
};
ObservableMap.prototype.set = function (key, value) {
    this.assertValidKey(key);
    key = "" + key;
    var hasKey = this._has(key);
    if (hasInterceptors(this)) {
        var change = interceptChange(this, {
            type: hasKey ? "update" : "add",
            object: this,
            newValue: value,
            name: key
        });
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype._updateHasMapEntry"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_updateHasMapEntry (key, value)](#apidoc.element.mobx.ObservableMap.prototype._updateHasMapEntry)
- description and source-code
```javascript
_updateHasMapEntry = function (key, value) {
    var entry = this._hasMap[key];
    if (entry) {
        entry.setNewValue(value);
    }
    else {
        entry = this._hasMap[key] = new ObservableValue(value, referenceEnhancer, this.name + "." + key + "?", false);
    }
    return entry;
}
```
- example usage
```shell
...
};
ObservableMap.prototype.has = function (key) {
    if (!this.isValidKey(key))
        return false;
    key = "" + key;
    if (this._hasMap[key])
        return this._hasMap[key].get();
    return this._updateHasMapEntry(key, false).get();
};
ObservableMap.prototype.set = function (key, value) {
    this.assertValidKey(key);
    key = "" + key;
    var hasKey = this._has(key);
    if (hasInterceptors(this)) {
        var change = interceptChange(this, {
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype._updateValue"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>_updateValue (name, newValue)](#apidoc.element.mobx.ObservableMap.prototype._updateValue)
- description and source-code
```javascript
_updateValue = function (name, newValue) {
    var observable = this._data[name];
    newValue = observable.prepareNewValue(newValue);
    if (newValue !== UNCHANGED) {
        var notifySpy = isSpyEnabled();
        var notify = hasListeners(this);
        var change = notify || notifySpy ? {
            type: "update",
            object: this,
            oldValue: observable.value,
            name: name, newValue: newValue
        } : null;
        if (notifySpy)
            spyReportStart(change);
        observable.setNewValue(newValue);
        if (notify)
            notifyListeners(this, change);
        if (notifySpy)
            spyReportEnd();
    }
}
```
- example usage
```shell
...
            name: key
        });
        if (!change)
            return this;
        value = change.newValue;
    }
    if (hasKey) {
        this._updateValue(key, value);
    }
    else {
        this._addValue(key, value);
    }
    return this;
};
ObservableMap.prototype.delete = function (key) {
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.assertValidKey"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>assertValidKey (key)](#apidoc.element.mobx.ObservableMap.prototype.assertValidKey)
- description and source-code
```javascript
assertValidKey = function (key) {
    if (!this.isValidKey(key))
        throw new Error("[mobx.map] Invalid key: '" + key + "', only strings, numbers and booleans are accepted as key in observable
 maps.");
}
```
- example usage
```shell
...
        return false;
    key = "" + key;
    if (this._hasMap[key])
        return this._hasMap[key].get();
    return this._updateHasMapEntry(key, false).get();
};
ObservableMap.prototype.set = function (key, value) {
    this.assertValidKey(key);
    key = "" + key;
    var hasKey = this._has(key);
    if (hasInterceptors(this)) {
        var change = interceptChange(this, {
            type: hasKey ? "update" : "add",
            object: this,
            newValue: value,
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.clear"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>clear ()](#apidoc.element.mobx.ObservableMap.prototype.clear)
- description and source-code
```javascript
clear = function () {
    var _this = this;
    runInTransaction(function () {
        untracked(function () {
            _this.keys().forEach(_this.delete, _this);
        });
    });
}
```
- example usage
```shell
...
            _this.keys().forEach(_this.delete, _this);
        });
    });
};
ObservableMap.prototype.replace = function (values) {
    var _this = this;
    runInTransaction(function () {
        _this.clear();
        _this.merge(values);
    });
    return this;
};
Object.defineProperty(ObservableMap.prototype, "size", {
    get: function () {
        return this._keys.length;
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.delete"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>delete (key)](#apidoc.element.mobx.ObservableMap.prototype.delete)
- description and source-code
```javascript
delete = function (key) {
    var _this = this;
    this.assertValidKey(key);
    key = "" + key;
    if (hasInterceptors(this)) {
        var change = interceptChange(this, {
            type: "delete",
            object: this,
            name: key
        });
        if (!change)
            return false;
    }
    if (this._has(key)) {
        var notifySpy = isSpyEnabled();
        var notify = hasListeners(this);
        var change = notify || notifySpy ? {
            type: "delete",
            object: this,
            oldValue: this._data[key].value,
            name: key
        } : null;
        if (notifySpy)
            spyReportStart(change);
        runInTransaction(function () {
            _this._keys.remove(key);
            _this._updateHasMapEntry(key, false);
            var observable = _this._data[key];
            observable.setNewValue(undefined);
            _this._data[key] = undefined;
        });
        if (notify)
            notifyListeners(this, change);
        if (notifySpy)
            spyReportEnd();
        return true;
    }
    return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.entries"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>entries ()](#apidoc.element.mobx.ObservableMap.prototype.entries)
- description and source-code
```javascript
entries = function () {
    var _this = this;
    return arrayAsIterator(this._keys.map(function (key) { return [key, _this.get(key)]; }));
}
```
- example usage
```shell
...
    ObservableMap.prototype.intercept = function (handler) {
        return registerInterceptor(this, handler);
    };
    return ObservableMap;
}());
exports.ObservableMap = ObservableMap;
declareIterator(ObservableMap.prototype, function () {
    return this.entries();
});
function map(initialValues) {
    deprecated("'mobx.map' is deprecated, use 'new ObservableMap' or 'mobx.observable.map' instead");
    return observable.map(initialValues);
}
exports.map = map;
var isObservableMap = createInstanceofPredicate("ObservableMap", ObservableMap);
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.forEach"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>forEach (callback, thisArg)](#apidoc.element.mobx.ObservableMap.prototype.forEach)
- description and source-code
```javascript
forEach = function (callback, thisArg) {
    var _this = this;
    this.keys().forEach(function (key) { return callback.call(thisArg, _this.get(key), key, _this); });
}
```
- example usage
```shell
...
return extendObservableHelper(target, referenceEnhancer, properties);
}
exports.extendShallowObservable = extendShallowObservable;
function extendObservableHelper(target, defaultEnhancer, properties) {
invariant(arguments.length >= 2, getMessage("m014"));
invariant(typeof target === "object", getMessage("m015"));
invariant(!(isObservableMap(target)), getMessage("m016"));
properties.forEach(function (propSet) {
    invariant(typeof propSet === "object", getMessage("m017"));
    invariant(!isObservable(propSet), getMessage("m018"));
});
var adm = asObservableObject(target);
var definedProps = {};
for (var i = properties.length - 1; i >= 0; i--) {
    var propSet = properties[i];
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.get"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>get (key)](#apidoc.element.mobx.ObservableMap.prototype.get)
- description and source-code
```javascript
get = function (key) {
    key = "" + key;
    if (this.has(key))
        return this._data[key].get();
    return undefined;
}
```
- example usage
```shell
...
        invariant(typeof originalDescriptor.get === "function", getMessage("m010"));
        var adm = asObservableObject(target, "");
        defineComputedProperty(adm, name, originalDescriptor.get, originalDescriptor.set, compareStructural, false);
    }, function (name) {
        var observable = this.$mobx.values[name];
        if (observable === undefined)
            return undefined;
        return observable.get();
    }, function (name, value) {
        this.$mobx.values[name].set(value);
    }, false, false);
}
var computedDecorator = createComputedDecorator(false);
var computedStructDecorator = createComputedDecorator(true);
var computed = (function computed(arg1, arg2, arg3) {
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.has"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>has (key)](#apidoc.element.mobx.ObservableMap.prototype.has)
- description and source-code
```javascript
has = function (key) {
    if (!this.isValidKey(key))
        return false;
    key = "" + key;
    if (this._hasMap[key])
        return this._hasMap[key].get();
    return this._updateHasMapEntry(key, false).get();
}
```
- example usage
```shell
...
    if (notify)
        notifyListeners(this, change);
    if (notifySpy)
        spyReportEnd();
};
ObservableMap.prototype.get = function (key) {
    key = "" + key;
    if (this.has(key))
        return this._data[key].get();
    return undefined;
};
ObservableMap.prototype.keys = function () {
    return arrayAsIterator(this._keys.slice());
};
ObservableMap.prototype.values = function () {
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.intercept"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>intercept (handler)](#apidoc.element.mobx.ObservableMap.prototype.intercept)
- description and source-code
```javascript
intercept = function (handler) {
    return registerInterceptor(this, handler);
}
```
- example usage
```shell
...
if (typeof handler === "function")
    return interceptProperty(thing, propOrHandler, handler);
else
    return interceptInterceptable(thing, propOrHandler);
}
exports.intercept = intercept;
function interceptInterceptable(thing, handler) {
return getAdministration(thing).intercept(handler);
}
function interceptProperty(thing, property, handler) {
return getAdministration(thing, property).intercept(handler);
}
function isComputed(value, property) {
if (value === null || value === undefined)
    return false;
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.isValidKey"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>isValidKey (key)](#apidoc.element.mobx.ObservableMap.prototype.isValidKey)
- description and source-code
```javascript
isValidKey = function (key) {
    if (key === null || key === undefined)
        return false;
    if (typeof key === "string" || typeof key === "number" || typeof key === "boolean")
        return true;
    return false;
}
```
- example usage
```shell
...
    this.changeListeners = null;
    this.merge(initialData);
}
ObservableMap.prototype._has = function (key) {
    return typeof this._data[key] !== "undefined";
};
ObservableMap.prototype.has = function (key) {
    if (!this.isValidKey(key))
        return false;
    key = "" + key;
    if (this._hasMap[key])
        return this._hasMap[key].get();
    return this._updateHasMapEntry(key, false).get();
};
ObservableMap.prototype.set = function (key, value) {
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.keys"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>keys ()](#apidoc.element.mobx.ObservableMap.prototype.keys)
- description and source-code
```javascript
keys = function () {
    return arrayAsIterator(this._keys.slice());
}
```
- example usage
```shell
...
    }
};
return IObservableFactories;
}());
exports.IObservableFactories = IObservableFactories;
var observable = createObservable;
exports.observable = observable;
Object.keys(IObservableFactories.prototype).forEach(function (key) { return observable[key] = IObservableFactories.prototype[key
]; });
observable.deep.struct = observable.struct;
observable.ref.struct = function () {
if (arguments.length < 2) {
    return createModifierDescriptor(refStructEnhancer, arguments[0]);
}
else {
    return refStructDecorator.apply(null, arguments);
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.merge"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>merge (other)](#apidoc.element.mobx.ObservableMap.prototype.merge)
- description and source-code
```javascript
merge = function (other) {
    var _this = this;
    if (isObservableMap(other)) {
        other = other.toJS();
    }
    runInTransaction(function () {
        if (isPlainObject(other))
            Object.keys(other).forEach(function (key) { return _this.set(key, other[key]); });
        else if (Array.isArray(other))
            other.forEach(function (_a) {
                var key = _a[0], value = _a[1];
                return _this.set(key, value);
            });
        else if (isES6Map(other))
            other.forEach(function (value, key) { return _this.set(key, value); });
        else if (other !== null && other !== undefined)
            fail("Cannot initialize map from " + other);
    });
    return this;
}
```
- example usage
```shell
...
    this.name = name;
    this.$mobx = ObservableMapMarker;
    this._data = Object.create(null);
    this._hasMap = Object.create(null);
    this._keys = new ObservableArray(undefined, referenceEnhancer, this.name + ".keys()", true);
    this.interceptors = null;
    this.changeListeners = null;
    this.merge(initialData);
}
ObservableMap.prototype._has = function (key) {
    return typeof this._data[key] !== "undefined";
};
ObservableMap.prototype.has = function (key) {
    if (!this.isValidKey(key))
        return false;
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.observe"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>observe (listener, fireImmediately)](#apidoc.element.mobx.ObservableMap.prototype.observe)
- description and source-code
```javascript
observe = function (listener, fireImmediately) {
    invariant(fireImmediately !== true, getMessage("m033"));
    return registerListener(this, listener);
}
```
- example usage
```shell
...
if (typeof cbOrFire === "function")
    return observeObservableProperty(thing, propOrCb, cbOrFire, fireImmediately);
else
    return observeObservable(thing, propOrCb, cbOrFire);
}
exports.observe = observe;
function observeObservable(thing, listener, fireImmediately) {
return getAdministration(thing).observe(listener, fireImmediately);
}
function observeObservableProperty(thing, property, listener, fireImmediately) {
return getAdministration(thing, property).observe(listener, fireImmediately);
}
function toJS(source, detectCycles, __alreadySeen) {
if (detectCycles === void 0) { detectCycles = true; }
if (__alreadySeen === void 0) { __alreadySeen = []; }
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.replace"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>replace (values)](#apidoc.element.mobx.ObservableMap.prototype.replace)
- description and source-code
```javascript
replace = function (values) {
    var _this = this;
    runInTransaction(function () {
        _this.clear();
        _this.merge(values);
    });
    return this;
}
```
- example usage
```shell
...
    var newItems;
    if (fromIndex < toIndex) {
        newItems = oldItems.slice(0, fromIndex).concat(oldItems.slice(fromIndex + 1, toIndex + 1), [oldItems[fromIndex]], oldItems
.slice(toIndex + 1));
    }
    else {
        newItems = oldItems.slice(0, toIndex).concat([oldItems[fromIndex]], oldItems.slice(toIndex, fromIndex), oldItems.slice(fromIndex
 + 1));
    }
    this.replace(newItems);
};
ObservableArray.prototype.toString = function () {
    this.$mobx.atom.reportObserved();
    return Array.prototype.toString.apply(this.$mobx.values, arguments);
};
ObservableArray.prototype.toLocaleString = function () {
    this.$mobx.atom.reportObserved();
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.set"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>set (key, value)](#apidoc.element.mobx.ObservableMap.prototype.set)
- description and source-code
```javascript
set = function (key, value) {
    this.assertValidKey(key);
    key = "" + key;
    var hasKey = this._has(key);
    if (hasInterceptors(this)) {
        var change = interceptChange(this, {
            type: hasKey ? "update" : "add",
            object: this,
            newValue: value,
            name: key
        });
        if (!change)
            return this;
        value = change.newValue;
    }
    if (hasKey) {
        this._updateValue(key, value);
    }
    else {
        this._addValue(key, value);
    }
    return this;
}
```
- example usage
```shell
...
    defineComputedProperty(adm, name, originalDescriptor.get, originalDescriptor.set, compareStructural, false);
}, function (name) {
    var observable = this.$mobx.values[name];
    if (observable === undefined)
        return undefined;
    return observable.get();
}, function (name, value) {
    this.$mobx.values[name].set(value);
}, false, false);
}
var computedDecorator = createComputedDecorator(false);
var computedStructDecorator = createComputedDecorator(true);
var computed = (function computed(arg1, arg2, arg3) {
if (typeof arg2 === "string") {
    return computedDecorator.apply(null, arguments);
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.toJS"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>toJS ()](#apidoc.element.mobx.ObservableMap.prototype.toJS)
- description and source-code
```javascript
toJS = function () {
    var _this = this;
    var res = {};
    this.keys().forEach(function (key) { return res[key] = _this.get(key); });
    return res;
}
```
- example usage
```shell
...
ObservableArray.prototype.replace = function (newItems) {
    return this.$mobx.spliceWithArray(0, this.$mobx.values.length, newItems);
};
ObservableArray.prototype.toJS = function () {
    return this.slice();
};
ObservableArray.prototype.toJSON = function () {
    return this.toJS();
};
ObservableArray.prototype.peek = function () {
    return this.$mobx.values;
};
ObservableArray.prototype.find = function (predicate, thisArg, fromIndex) {
    if (fromIndex === void 0) { fromIndex = 0; }
    this.$mobx.atom.reportObserved();
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.toJSON"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>toJSON ()](#apidoc.element.mobx.ObservableMap.prototype.toJSON)
- description and source-code
```javascript
toJSON = function () {
    return this.toJS();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.toString"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>toString ()](#apidoc.element.mobx.ObservableMap.prototype.toString)
- description and source-code
```javascript
toString = function () {
    var _this = this;
    return this.name + "[{ " + this.keys().map(function (key) { return key + ": " + ("" + _this.get(key)); }).join(", ") + " }]";
}
```
- example usage
```shell
...
        prevValue = newValue;
    });
};
ComputedValue.prototype.toJSON = function () {
    return this.get();
};
ComputedValue.prototype.toString = function () {
    return this.name + "[" + this.derivation.toString() + "]";
};
ComputedValue.prototype.valueOf = function () {
    return toPrimitive(this.get());
};
;
ComputedValue.prototype.whyRun = function () {
    var isTracking = Boolean(globalState.trackingDerivation);
...
```

#### <a name="apidoc.element.mobx.ObservableMap.prototype.values"></a>[function <span class="apidocSignatureSpan">mobx.ObservableMap.prototype.</span>values ()](#apidoc.element.mobx.ObservableMap.prototype.values)
- description and source-code
```javascript
values = function () {
    return arrayAsIterator(this._keys.map(this.get, this));
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.Reaction"></a>[module mobx.Reaction](#apidoc.module.mobx.Reaction)

#### <a name="apidoc.element.mobx.Reaction.Reaction"></a>[function <span class="apidocSignatureSpan">mobx.</span>Reaction (name, onInvalidate)](#apidoc.element.mobx.Reaction.Reaction)
- description and source-code
```javascript
function Reaction(name, onInvalidate) {
    if (name === void 0) { name = "Reaction@" + getNextId(); }
    this.name = name;
    this.onInvalidate = onInvalidate;
    this.observing = [];
    this.newObserving = [];
    this.dependenciesState = IDerivationState.NOT_TRACKING;
    this.diffValue = 0;
    this.runId = 0;
    this.unboundDepsCount = 0;
    this.__mapid = "#" + getNextId();
    this.isDisposed = false;
    this._isScheduled = false;
    this._isTrackPending = false;
    this._isRunning = false;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.Reaction.prototype"></a>[module mobx.Reaction.prototype](#apidoc.module.mobx.Reaction.prototype)

#### <a name="apidoc.element.mobx.Reaction.prototype.dispose"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>dispose ()](#apidoc.element.mobx.Reaction.prototype.dispose)
- description and source-code
```javascript
dispose = function () {
    if (!this.isDisposed) {
        this.isDisposed = true;
        if (!this._isRunning) {
            startBatch();
            clearObserving(this);
            endBatch();
        }
    }
}
```
- example usage
```shell
...
        name = ("When@" + getNextId());
        predicate = arg1;
        effect = arg2;
        scope = arg3;
    }
    var disposer = autorun(name, function (r) {
        if (predicate.call(scope)) {
            r.dispose();
            var prevUntracked = untrackedStart();
            effect.call(scope);
            untrackedEnd(prevUntracked);
        }
    });
    return disposer;
}
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.getDisposer"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>getDisposer ()](#apidoc.element.mobx.Reaction.prototype.getDisposer)
- description and source-code
```javascript
getDisposer = function () {
    var r = this.dispose.bind(this);
    r.$mobx = this;
    r.onError = registerErrorHandler;
    return r;
}
```
- example usage
```shell
...
var reaction = new Reaction(name, function () {
    this.track(reactionRunner);
});
function reactionRunner() {
    view(reaction);
}
reaction.schedule();
return reaction.getDisposer();
}
exports.autorun = autorun;
function when(arg1, arg2, arg3, arg4) {
var name, predicate, effect, scope;
if (typeof arg1 === "string") {
    name = arg1;
    predicate = arg2;
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.isScheduled"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>isScheduled ()](#apidoc.element.mobx.Reaction.prototype.isScheduled)
- description and source-code
```javascript
isScheduled = function () {
    return this._isScheduled;
}
```
- example usage
```shell
...
    return r;
};
Reaction.prototype.toString = function () {
    return "Reaction[" + this.name + "]";
};
Reaction.prototype.whyRun = function () {
    var observing = unique(this._isRunning ? this.newObserving : this.observing).map(function (dep) { return dep.name; });
    return ("\nWhyRun? reaction '" + this.name + "':\n * Status: [" + (this.isDisposed ? "stopped" : this._isRunning ? "running" :
this.isScheduled() ? "scheduled" : "idle") + "]\n * This reaction will re-run if any of the following observables changes:\n    " + joinStrings(observing) + "\n    " + ((this._isRunning) ? " (... or any observable accessed during the remainder of the current run)" : "") + "\n\t" + getMessage("m038") + "\n");
};
return Reaction;
}());
exports.Reaction = Reaction;
function registerErrorHandler(handler) {
invariant(this && this.$mobx && isReaction(this.$mobx), "Invalid 'this'");
invariant(!this.$mobx.errorHandler, "Only one onErrorHandler can be registered");
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.onBecomeStale"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>onBecomeStale ()](#apidoc.element.mobx.Reaction.prototype.onBecomeStale)
- description and source-code
```javascript
onBecomeStale = function () {
    this.schedule();
}
```
- example usage
```shell
...
    if (dep.diffValue === 1) {
        dep.diffValue = 0;
        addObserver(dep, derivation);
    }
}
if (lowestNewObservingDerivationState !== IDerivationState.UP_TO_DATE) {
    derivation.dependenciesState = lowestNewObservingDerivationState;
    derivation.onBecomeStale();
}
}
function clearObserving(derivation) {
var obs = derivation.observing;
var i = obs.length;
while (i--)
    removeObserver(obs[i], derivation);
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.reportExceptionInDerivation"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>reportExceptionInDerivation (error)](#apidoc.element.mobx.Reaction.prototype.reportExceptionInDerivation)
- description and source-code
```javascript
reportExceptionInDerivation = function (error) {
    var _this = this;
    if (this.errorHandler) {
        this.errorHandler(error, this);
        return;
    }
    var message = "[mobx] Encountered an uncaught exception that was thrown by a reaction or observer component, in: '" + this;
    var messageToUser = getMessage("m037");
    console.error(message || messageToUser, error);
    if (isSpyEnabled()) {
        spyReport({
            type: "error",
            message: message,
            error: error,
            object: this
        });
    }
    globalState.globalReactionErrorHandlers.forEach(function (f) { return f(error, _this); });
}
```
- example usage
```shell
...
    var result = trackDerivedFunction(this, fn, undefined);
    this._isRunning = false;
    this._isTrackPending = false;
    if (this.isDisposed) {
        clearObserving(this);
    }
    if (isCaughtException(result))
        this.reportExceptionInDerivation(result.cause);
    if (notify) {
        spyReportEnd({
            time: Date.now() - startTime
        });
    }
    endBatch();
};
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.runReaction"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>runReaction ()](#apidoc.element.mobx.Reaction.prototype.runReaction)
- description and source-code
```javascript
runReaction = function () {
    if (!this.isDisposed) {
        startBatch();
        this._isScheduled = false;
        if (shouldCompute(this)) {
            this._isTrackPending = true;
            this.onInvalidate();
            if (this._isTrackPending && isSpyEnabled()) {
                spyReport({
                    object: this,
                    type: "scheduled-reaction"
                });
            }
        }
        endBatch();
    }
}
```
- example usage
```shell
...
    if (++iterations === MAX_REACTION_ITERATIONS) {
        console.error("Reaction doesn't converge to a stable state after " + MAX_REACTION_ITERATIONS + " iterations."
            + (" Probably there is a cycle in the reactive function: " + allReactions[0]));
        allReactions.splice(0);
    }
    var remainingReactions = allReactions.splice(0);
    for (var i = 0, l = remainingReactions.length; i < l; i++)
        remainingReactions[i].runReaction();
}
globalState.isRunningReactions = false;
}
var isReaction = createInstanceofPredicate("Reaction", Reaction);
function setReactionScheduler(fn) {
var baseScheduler = reactionScheduler;
reactionScheduler = function (f) { return fn(function () { return baseScheduler(f); }); };
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.schedule"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>schedule ()](#apidoc.element.mobx.Reaction.prototype.schedule)
- description and source-code
```javascript
schedule = function () {
    if (!this._isScheduled) {
        this._isScheduled = true;
        globalState.pendingReactions.push(this);
        runReactions();
    }
}
```
- example usage
```shell
...
    view = view.bind(scope);
var reaction = new Reaction(name, function () {
    this.track(reactionRunner);
});
function reactionRunner() {
    view(reaction);
}
reaction.schedule();
return reaction.getDisposer();
}
exports.autorun = autorun;
function when(arg1, arg2, arg3, arg4) {
var name, predicate, effect, scope;
if (typeof arg1 === "string") {
    name = arg1;
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.toString"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>toString ()](#apidoc.element.mobx.Reaction.prototype.toString)
- description and source-code
```javascript
toString = function () {
    return "Reaction[" + this.name + "]";
}
```
- example usage
```shell
...
        prevValue = newValue;
    });
};
ComputedValue.prototype.toJSON = function () {
    return this.get();
};
ComputedValue.prototype.toString = function () {
    return this.name + "[" + this.derivation.toString() + "]";
};
ComputedValue.prototype.valueOf = function () {
    return toPrimitive(this.get());
};
;
ComputedValue.prototype.whyRun = function () {
    var isTracking = Boolean(globalState.trackingDerivation);
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.track"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>track (fn)](#apidoc.element.mobx.Reaction.prototype.track)
- description and source-code
```javascript
track = function (fn) {
    startBatch();
    var notify = isSpyEnabled();
    var startTime;
    if (notify) {
        startTime = Date.now();
        spyReportStart({
            object: this,
            type: "reaction",
            fn: fn
        });
    }
    this._isRunning = true;
    var result = trackDerivedFunction(this, fn, undefined);
    this._isRunning = false;
    this._isTrackPending = false;
    if (this.isDisposed) {
        clearObserving(this);
    }
    if (isCaughtException(result))
        this.reportExceptionInDerivation(result.cause);
    if (notify) {
        spyReportEnd({
            time: Date.now() - startTime
        });
    }
    endBatch();
}
```
- example usage
```shell
...
        scope = arg2;
    }
    invariant(typeof view === "function", getMessage("m004"));
    invariant(isAction(view) === false, getMessage("m005"));
    if (scope)
        view = view.bind(scope);
    var reaction = new Reaction(name, function () {
        this.track(reactionRunner);
    });
    function reactionRunner() {
        view(reaction);
    }
    reaction.schedule();
    return reaction.getDisposer();
}
...
```

#### <a name="apidoc.element.mobx.Reaction.prototype.whyRun"></a>[function <span class="apidocSignatureSpan">mobx.Reaction.prototype.</span>whyRun ()](#apidoc.element.mobx.Reaction.prototype.whyRun)
- description and source-code
```javascript
whyRun = function () {
    var observing = unique(this._isRunning ? this.newObserving : this.observing).map(function (dep) { return dep.name; });
    return ("\nWhyRun? reaction '" + this.name + "':\n * Status: [" + (this.isDisposed ? "stopped" : this._isRunning ? "running" :
this.isScheduled() ? "scheduled" : "idle") + "]\n * This reaction will re-run if any of the following observables changes:\n    " + joinStrings(observing) + "\n    " + ((this._isRunning) ? " (... or any observable accessed during the remainder of the current run)" : "") + "\n\t" + getMessage("m038") + "\n");
}
```
- example usage
```shell
...
        break;
    case 2:
        thing = getAtom(thing, prop);
        break;
}
thing = getAtom(thing);
if (isComputedValue(thing))
    return log(thing.whyRun());
else if (isReaction(thing))
    return log(thing.whyRun());
return fail(getMessage("m025"));
}
exports.whyRun = whyRun;
function createAction(actionName, fn) {
invariant(typeof fn === "function", getMessage("m026"));
...
```



# <a name="apidoc.module.mobx.action"></a>[module mobx.action](#apidoc.module.mobx.action)

#### <a name="apidoc.element.mobx.action.action"></a>[function <span class="apidocSignatureSpan">mobx.</span>action (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.action.action)
- description and source-code
```javascript
function action(arg1, arg2, arg3, arg4) {
    if (arguments.length === 1 && typeof arg1 === "function")
        return createAction(arg1.name || "<unnamed action>", arg1);
    if (arguments.length === 2 && typeof arg2 === "function")
        return createAction(arg1, arg2);
    if (arguments.length === 1 && typeof arg1 === "string")
        return namedActionDecorator(arg1);
    return namedActionDecorator(arg2).apply(null, arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.action.bound"></a>[function <span class="apidocSignatureSpan">mobx.action.</span>bound (arg1, arg2, arg3)](#apidoc.element.mobx.action.bound)
- description and source-code
```javascript
function boundAction(arg1, arg2, arg3) {
    if (typeof arg1 === "function") {
        var action_1 = createAction("<not yet bound action>", arg1);
        action_1.autoBind = true;
        return action_1;
    }
    return boundActionDecorator.apply(null, arguments);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.computed"></a>[module mobx.computed](#apidoc.module.mobx.computed)

#### <a name="apidoc.element.mobx.computed.computed"></a>[function <span class="apidocSignatureSpan">mobx.</span>computed (arg1, arg2, arg3)](#apidoc.element.mobx.computed.computed)
- description and source-code
```javascript
function computed(arg1, arg2, arg3) {
    if (typeof arg2 === "string") {
        return computedDecorator.apply(null, arguments);
    }
    invariant(typeof arg1 === "function", getMessage("m011"));
    invariant(arguments.length < 3, getMessage("m012"));
    var opts = typeof arg2 === "object" ? arg2 : {};
    opts.setter = typeof arg2 === "function" ? arg2 : opts.setter;
    return new ComputedValue(arg1, opts.context, opts.compareStructural || opts.struct || false, opts.name || arg1.name || "", opts
.setter);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.computed.struct"></a>[function <span class="apidocSignatureSpan">mobx.computed.</span>struct (target, key, descriptor, customArgs, argLen)](#apidoc.element.mobx.computed.struct)
- description and source-code
```javascript
function classPropertyDecorator(target, key, descriptor, customArgs, argLen) {
    if (argLen === void 0) { argLen = 0; }
    invariant(allowCustomArguments || quacksLikeADecorator(arguments), "This function is a decorator, but it wasn't invoked like
 a decorator");
    if (!descriptor) {
        var newDescriptor = {
            enumerable: enumerable,
            configurable: true,
            get: function () {
                if (!this.__mobxInitializedProps || this.__mobxInitializedProps[key] !== true)
                    typescriptInitializeProperty(this, key, undefined, onInitialize, customArgs, descriptor);
                return get.call(this, key);
            },
            set: function (v) {
                if (!this.__mobxInitializedProps || this.__mobxInitializedProps[key] !== true) {
                    typescriptInitializeProperty(this, key, v, onInitialize, customArgs, descriptor);
                }
                else {
                    set.call(this, key, v);
                }
            }
        };
        if (arguments.length < 3 || arguments.length === 5 && argLen < 3) {
            Object.defineProperty(target, key, newDescriptor);
        }
        return newDescriptor;
    }
    else {
        if (!hasOwnProperty(target, "__mobxLazyInitializers")) {
            addHiddenProp(target, "__mobxLazyInitializers", (target.__mobxLazyInitializers && target.__mobxLazyInitializers.slice
()) || []);
        }
        var value_1 = descriptor.value, initializer_1 = descriptor.initializer;
        target.__mobxLazyInitializers.push(function (instance) {
            onInitialize(instance, key, (initializer_1 ? initializer_1.call(instance) : value_1), customArgs, descriptor);
        });
        return {
            enumerable: enumerable, configurable: true,
            get: function () {
                if (this.__mobxDidRunLazyInitializers !== true)
                    runLazyInitializers(this);
                return get.call(this, key);
            },
            set: function (v) {
                if (this.__mobxDidRunLazyInitializers !== true)
                    runLazyInitializers(this);
                set.call(this, key, v);
            }
        };
    }
}
```
- example usage
```shell
...
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
...
```



# <a name="apidoc.module.mobx.extras"></a>[module mobx.extras](#apidoc.module.mobx.extras)

#### <a name="apidoc.element.mobx.extras.allowStateChanges"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>allowStateChanges (allowStateChanges, func)](#apidoc.element.mobx.extras.allowStateChanges)
- description and source-code
```javascript
function allowStateChanges(allowStateChanges, func) {
    var prev = allowStateChangesStart(allowStateChanges);
    var res;
    try {
        res = func();
    }
    finally {
        allowStateChangesEnd(prev);
    }
    return res;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.deepEqual"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>deepEqual (a, b)](#apidoc.element.mobx.extras.deepEqual)
- description and source-code
```javascript
function deepEqual(a, b) {
    if (a === null && b === null)
        return true;
    if (a === undefined && b === undefined)
        return true;
    if (typeof a !== "object")
        return a === b;
    var aIsArray = isArrayLike(a);
    var aIsMap = isMapLike(a);
    if (aIsArray !== isArrayLike(b)) {
        return false;
    }
    else if (aIsMap !== isMapLike(b)) {
        return false;
    }
    else if (aIsArray) {
        if (a.length !== b.length)
            return false;
        for (var i = a.length - 1; i >= 0; i--)
            if (!deepEqual(a[i], b[i]))
                return false;
        return true;
    }
    else if (aIsMap) {
        if (a.size !== b.size)
            return false;
        var equals_1 = true;
        a.forEach(function (value, key) {
            equals_1 = equals_1 && deepEqual(b.get(key), value);
        });
        return equals_1;
    }
    else if (typeof a === "object" && typeof b === "object") {
        if (a === null || b === null)
            return false;
        if (isMapLike(a) && isMapLike(b)) {
            if (a.size !== b.size)
                return false;
            return deepEqual(observable.shallowMap(a).entries(), observable.shallowMap(b).entries());
        }
        if (getEnumerableKeys(a).length !== getEnumerableKeys(b).length)
            return false;
        for (var prop in a) {
            if (!(prop in b))
                return false;
            if (!deepEqual(a[prop], b[prop]))
                return false;
        }
        return true;
    }
    return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.getAdministration"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>getAdministration (thing, property)](#apidoc.element.mobx.extras.getAdministration)
- description and source-code
```javascript
function getAdministration(thing, property) {
    invariant(thing, "Expecting some object");
    if (property !== undefined)
        return getAdministration(getAtom(thing, property));
    if (isAtom(thing) || isComputedValue(thing) || isReaction(thing))
        return thing;
    if (isObservableMap(thing))
        return thing;
    runLazyInitializers(thing);
    if (thing.$mobx)
        return thing.$mobx;
    invariant(false, "Cannot obtain administration from " + thing);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.getAtom"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>getAtom (thing, property)](#apidoc.element.mobx.extras.getAtom)
- description and source-code
```javascript
function getAtom(thing, property) {
    if (typeof thing === "object" && thing !== null) {
        if (isObservableArray(thing)) {
            invariant(property === undefined, getMessage("m036"));
            return thing.$mobx.atom;
        }
        if (isObservableMap(thing)) {
            var anyThing = thing;
            if (property === undefined)
                return getAtom(anyThing._keys);
            var observable_2 = anyThing._data[property] || anyThing._hasMap[property];
            invariant(!!observable_2, "the entry '" + property + "' does not exist in the observable map '" + getDebugName(thing
) + "'");
            return observable_2;
        }
        runLazyInitializers(thing);
        if (isObservableObject(thing)) {
            if (!property)
                return fail("please specify a property");
            var observable_3 = thing.$mobx.values[property];
            invariant(!!observable_3, "no observable property '" + property + "' found on the observable object '" + getDebugName
(thing) + "'");
            return observable_3;
        }
        if (isAtom(thing) || isComputedValue(thing) || isReaction(thing)) {
            return thing;
        }
    }
    else if (typeof thing === "function") {
        if (isReaction(thing.$mobx)) {
            return thing.$mobx;
        }
    }
    return fail("Cannot obtain atom from " + thing);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.getDebugName"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>getDebugName (thing, property)](#apidoc.element.mobx.extras.getDebugName)
- description and source-code
```javascript
function getDebugName(thing, property) {
    var named;
    if (property !== undefined)
        named = getAtom(thing, property);
    else if (isObservableObject(thing) || isObservableMap(thing))
        named = getAdministration(thing);
    else
        named = getAtom(thing);
    return named.name;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.getDependencyTree"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>getDependencyTree (thing, property)](#apidoc.element.mobx.extras.getDependencyTree)
- description and source-code
```javascript
function getDependencyTree(thing, property) {
    return nodeToDependencyTree(getAtom(thing, property));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.getGlobalState"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>getGlobalState ()](#apidoc.element.mobx.extras.getGlobalState)
- description and source-code
```javascript
function getGlobalState() {
    return globalState;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.getObserverTree"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>getObserverTree (thing, property)](#apidoc.element.mobx.extras.getObserverTree)
- description and source-code
```javascript
function getObserverTree(thing, property) {
    return nodeToObserverTree(getAtom(thing, property));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.isComputingDerivation"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>isComputingDerivation ()](#apidoc.element.mobx.extras.isComputingDerivation)
- description and source-code
```javascript
function isComputingDerivation() {
    return globalState.trackingDerivation !== null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.isSpyEnabled"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>isSpyEnabled ()](#apidoc.element.mobx.extras.isSpyEnabled)
- description and source-code
```javascript
function isSpyEnabled() {
    return !!globalState.spyListeners.length;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.onReactionError"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>onReactionError (handler)](#apidoc.element.mobx.extras.onReactionError)
- description and source-code
```javascript
function onReactionError(handler) {
    globalState.globalReactionErrorHandlers.push(handler);
    return function () {
        var idx = globalState.globalReactionErrorHandlers.indexOf(handler);
        if (idx >= 0)
            globalState.globalReactionErrorHandlers.splice(idx, 1);
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.resetGlobalState"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>resetGlobalState ()](#apidoc.element.mobx.extras.resetGlobalState)
- description and source-code
```javascript
function resetGlobalState() {
    globalState.resetId++;
    var defaultGlobals = new MobXGlobals();
    for (var key in defaultGlobals)
        if (persistentKeys.indexOf(key) === -1)
            globalState[key] = defaultGlobals[key];
    globalState.allowStateChanges = !globalState.strictMode;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.setReactionScheduler"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>setReactionScheduler (fn)](#apidoc.element.mobx.extras.setReactionScheduler)
- description and source-code
```javascript
function setReactionScheduler(fn) {
    var baseScheduler = reactionScheduler;
    reactionScheduler = function (f) { return fn(function () { return baseScheduler(f); }); };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.shareGlobalState"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>shareGlobalState ()](#apidoc.element.mobx.extras.shareGlobalState)
- description and source-code
```javascript
function shareGlobalState() {
    var global = getGlobal();
    var ownState = globalState;
    if (global.__mobservableTrackingStack || global.__mobservableViewStack)
        throw new Error("[mobx] An incompatible version of mobservable is already loaded.");
    if (global.__mobxGlobal && global.__mobxGlobal.version !== ownState.version)
        throw new Error("[mobx] An incompatible version of mobx is already loaded.");
    if (global.__mobxGlobal)
        globalState = global.__mobxGlobal;
    else
        global.__mobxGlobal = ownState;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.spyReport"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>spyReport (event)](#apidoc.element.mobx.extras.spyReport)
- description and source-code
```javascript
function spyReport(event) {
    if (!globalState.spyListeners.length)
        return;
    var listeners = globalState.spyListeners;
    for (var i = 0, l = listeners.length; i < l; i++)
        listeners[i](event);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.spyReportEnd"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>spyReportEnd (change)](#apidoc.element.mobx.extras.spyReportEnd)
- description and source-code
```javascript
function spyReportEnd(change) {
    if (change)
        spyReport(objectAssign({}, change, END_EVENT));
    else
        spyReport(END_EVENT);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.extras.spyReportStart"></a>[function <span class="apidocSignatureSpan">mobx.extras.</span>spyReportStart (event)](#apidoc.element.mobx.extras.spyReportStart)
- description and source-code
```javascript
function spyReportStart(event) {
    var change = objectAssign({}, event, { spyReportStart: true });
    spyReport(change);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.mobx.mobx_umd"></a>[module mobx.mobx_umd](#apidoc.module.mobx.mobx_umd)

#### <a name="apidoc.element.mobx.mobx_umd.Atom"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>Atom (name, onBecomeObservedHandler, onBecomeUnobservedHandler)](#apidoc.element.mobx.mobx_umd.Atom)
- description and source-code
```javascript
function Atom(name, onBecomeObservedHandler, onBecomeUnobservedHandler) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    if (onBecomeObservedHandler === void 0) { onBecomeObservedHandler = noop; }
    if (onBecomeUnobservedHandler === void 0) { onBecomeUnobservedHandler = noop; }
    var _this = _super.call(this, name) || this;
    _this.name = name;
    _this.onBecomeObservedHandler = onBecomeObservedHandler;
    _this.onBecomeUnobservedHandler = onBecomeUnobservedHandler;
    _this.isPendingUnobservation = false;
    _this.isBeingTracked = false;
    return _this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.BaseAtom"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>BaseAtom (name)](#apidoc.element.mobx.mobx_umd.BaseAtom)
- description and source-code
```javascript
function BaseAtom(name) {
    if (name === void 0) { name = "Atom@" + getNextId(); }
    this.name = name;
    this.isPendingUnobservation = true;
    this.observers = [];
    this.observersIndexes = {};
    this.diffValue = 0;
    this.lastAccessedBy = 0;
    this.lowestObserverState = IDerivationState.NOT_TRACKING;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.IObservableFactories"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>IObservableFactories ()](#apidoc.element.mobx.mobx_umd.IObservableFactories)
- description and source-code
```javascript
function IObservableFactories() {
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.ObservableMap"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>ObservableMap (initialData, enhancer, name)](#apidoc.element.mobx.mobx_umd.ObservableMap)
- description and source-code
```javascript
function ObservableMap(initialData, enhancer, name) {
    if (enhancer === void 0) { enhancer = deepEnhancer; }
    if (name === void 0) { name = "ObservableMap@" + getNextId(); }
    this.enhancer = enhancer;
    this.name = name;
    this.$mobx = ObservableMapMarker;
    this._data = Object.create(null);
    this._hasMap = Object.create(null);
    this._keys = new ObservableArray(undefined, referenceEnhancer, this.name + ".keys()", true);
    this.interceptors = null;
    this.changeListeners = null;
    this.merge(initialData);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.Reaction"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>Reaction (name, onInvalidate)](#apidoc.element.mobx.mobx_umd.Reaction)
- description and source-code
```javascript
function Reaction(name, onInvalidate) {
    if (name === void 0) { name = "Reaction@" + getNextId(); }
    this.name = name;
    this.onInvalidate = onInvalidate;
    this.observing = [];
    this.newObserving = [];
    this.dependenciesState = IDerivationState.NOT_TRACKING;
    this.diffValue = 0;
    this.runId = 0;
    this.unboundDepsCount = 0;
    this.__mapid = "#" + getNextId();
    this.isDisposed = false;
    this._isScheduled = false;
    this._isTrackPending = false;
    this._isRunning = false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.action"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>action (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.mobx_umd.action)
- description and source-code
```javascript
function action(arg1, arg2, arg3, arg4) {
    if (arguments.length === 1 && typeof arg1 === "function")
        return createAction(arg1.name || "<unnamed action>", arg1);
    if (arguments.length === 2 && typeof arg2 === "function")
        return createAction(arg1, arg2);
    if (arguments.length === 1 && typeof arg1 === "string")
        return namedActionDecorator(arg1);
    return namedActionDecorator(arg2).apply(null, arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.asFlat"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asFlat (value)](#apidoc.element.mobx.mobx_umd.asFlat)
- description and source-code
```javascript
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.asMap"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asMap (data)](#apidoc.element.mobx.mobx_umd.asMap)
- description and source-code
```javascript
function asMap(data) {
    deprecated("asMap is deprecated, use observable.map or observable.shallowMap instead");
    return observable.map(data || {});
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.asReference"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asReference (value)](#apidoc.element.mobx.mobx_umd.asReference)
- description and source-code
```javascript
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.asStructure"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>asStructure (value)](#apidoc.element.mobx.mobx_umd.asStructure)
- description and source-code
```javascript
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.autorun"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>autorun (arg1, arg2, arg3)](#apidoc.element.mobx.mobx_umd.autorun)
- description and source-code
```javascript
function autorun(arg1, arg2, arg3) {
    var name, view, scope;
    if (typeof arg1 === "string") {
        name = arg1;
        view = arg2;
        scope = arg3;
    }
    else {
        name = arg1.name || ("Autorun@" + getNextId());
        view = arg1;
        scope = arg2;
    }
    invariant(typeof view === "function", getMessage("m004"));
    invariant(isAction(view) === false, getMessage("m005"));
    if (scope)
        view = view.bind(scope);
    var reaction = new Reaction(name, function () {
        this.track(reactionRunner);
    });
    function reactionRunner() {
        view(reaction);
    }
    reaction.schedule();
    return reaction.getDisposer();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.autorunAsync"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>autorunAsync (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.mobx_umd.autorunAsync)
- description and source-code
```javascript
function autorunAsync(arg1, arg2, arg3, arg4) {
    var name, func, delay, scope;
    if (typeof arg1 === "string") {
        name = arg1;
        func = arg2;
        delay = arg3;
        scope = arg4;
    }
    else {
        name = arg1.name || ("AutorunAsync@" + getNextId());
        func = arg1;
        delay = arg2;
        scope = arg3;
    }
    invariant(isAction(func) === false, getMessage("m006"));
    if (delay === void 0)
        delay = 1;
    if (scope)
        func = func.bind(scope);
    var isScheduled = false;
    var r = new Reaction(name, function () {
        if (!isScheduled) {
            isScheduled = true;
            setTimeout(function () {
                isScheduled = false;
                if (!r.isDisposed)
                    r.track(reactionRunner);
            }, delay);
        }
    });
    function reactionRunner() { func(r); }
    r.schedule();
    return r.getDisposer();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.computed"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>computed (arg1, arg2, arg3)](#apidoc.element.mobx.mobx_umd.computed)
- description and source-code
```javascript
function computed(arg1, arg2, arg3) {
    if (typeof arg2 === "string") {
        return computedDecorator.apply(null, arguments);
    }
    invariant(typeof arg1 === "function", getMessage("m011"));
    invariant(arguments.length < 3, getMessage("m012"));
    var opts = typeof arg2 === "object" ? arg2 : {};
    opts.setter = typeof arg2 === "function" ? arg2 : opts.setter;
    return new ComputedValue(arg1, opts.context, opts.compareStructural || opts.struct || false, opts.name || arg1.name || "", opts
.setter);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.createTransformer"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>createTransformer (transformer, onCleanup)](#apidoc.element.mobx.mobx_umd.createTransformer)
- description and source-code
```javascript
function createTransformer(transformer, onCleanup) {
    invariant(typeof transformer === "function" && transformer.length < 2, "createTransformer expects a function that accepts one
 argument");
    var objectCache = {};
    var resetId = globalState.resetId;
    var Transformer = (function (_super) {
        __extends(Transformer, _super);
        function Transformer(sourceIdentifier, sourceObject) {
            var _this = _super.call(this, function () { return transformer(sourceObject); }, undefined, false, "Transformer-" +
transformer.name + "-" + sourceIdentifier, undefined) || this;
            _this.sourceIdentifier = sourceIdentifier;
            _this.sourceObject = sourceObject;
            return _this;
        }
        Transformer.prototype.onBecomeUnobserved = function () {
            var lastValue = this.value;
            _super.prototype.onBecomeUnobserved.call(this);
            delete objectCache[this.sourceIdentifier];
            if (onCleanup)
                onCleanup(lastValue, this.sourceObject);
        };
        return Transformer;
    }(ComputedValue));
    return function (object) {
        if (resetId !== globalState.resetId) {
            objectCache = {};
            resetId = globalState.resetId;
        }
        var identifier = getMemoizationId(object);
        var reactiveTransformer = objectCache[identifier];
        if (reactiveTransformer)
            return reactiveTransformer.get();
        reactiveTransformer = objectCache[identifier] = new Transformer(identifier, object);
        return reactiveTransformer.get();
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.expr"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>expr (expr, scope)](#apidoc.element.mobx.mobx_umd.expr)
- description and source-code
```javascript
function expr(expr, scope) {
    if (!isComputingDerivation())
        console.warn(getMessage("m013"));
    return computed(expr, { context: scope }).get();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.extendObservable"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>extendObservable (target)](#apidoc.element.mobx.mobx_umd.extendObservable)
- description and source-code
```javascript
function extendObservable(target) {
    var properties = [];
    for (var _i = 1; _i < arguments.length; _i++) {
        properties[_i - 1] = arguments[_i];
    }
    return extendObservableHelper(target, deepEnhancer, properties);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.extendShallowObservable"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>extendShallowObservable (target)](#apidoc.element.mobx.mobx_umd.extendShallowObservable)
- description and source-code
```javascript
function extendShallowObservable(target) {
    var properties = [];
    for (var _i = 1; _i < arguments.length; _i++) {
        properties[_i - 1] = arguments[_i];
    }
    return extendObservableHelper(target, referenceEnhancer, properties);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.intercept"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>intercept (thing, propOrHandler, handler)](#apidoc.element.mobx.mobx_umd.intercept)
- description and source-code
```javascript
function intercept(thing, propOrHandler, handler) {
    if (typeof handler === "function")
        return interceptProperty(thing, propOrHandler, handler);
    else
        return interceptInterceptable(thing, propOrHandler);
}
```
- example usage
```shell
...
if (typeof handler === "function")
    return interceptProperty(thing, propOrHandler, handler);
else
    return interceptInterceptable(thing, propOrHandler);
}
exports.intercept = intercept;
function interceptInterceptable(thing, handler) {
return getAdministration(thing).intercept(handler);
}
function interceptProperty(thing, property, handler) {
return getAdministration(thing, property).intercept(handler);
}
function isComputed(value, property) {
if (value === null || value === undefined)
    return false;
...
```

#### <a name="apidoc.element.mobx.mobx_umd.isAction"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isAction (thing)](#apidoc.element.mobx.mobx_umd.isAction)
- description and source-code
```javascript
function isAction(thing) {
    return typeof thing === "function" && thing.isMobxAction === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isArrayLike"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isArrayLike (x)](#apidoc.element.mobx.mobx_umd.isArrayLike)
- description and source-code
```javascript
function isArrayLike(x) {
    return Array.isArray(x) || isObservableArray(x);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isBoxedObservable"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isBoxedObservable (x)](#apidoc.element.mobx.mobx_umd.isBoxedObservable)
- description and source-code
```javascript
isBoxedObservable = function (x) {
    return isObject(x) && x[propName] === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isComputed"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isComputed (value, property)](#apidoc.element.mobx.mobx_umd.isComputed)
- description and source-code
```javascript
function isComputed(value, property) {
    if (value === null || value === undefined)
        return false;
    if (property !== undefined) {
        if (isObservableObject(value) === false)
            return false;
        var atom = getAtom(value, property);
        return isComputedValue(atom);
    }
    return isComputedValue(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isModifierDescriptor"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isModifierDescriptor (thing)](#apidoc.element.mobx.mobx_umd.isModifierDescriptor)
- description and source-code
```javascript
function isModifierDescriptor(thing) {
    return typeof thing === "object" && thing !== null && thing.isMobxModifierDescriptor === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isObservable"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservable (value, property)](#apidoc.element.mobx.mobx_umd.isObservable)
- description and source-code
```javascript
function isObservable(value, property) {
    if (value === null || value === undefined)
        return false;
    if (property !== undefined) {
        if (isObservableArray(value) || isObservableMap(value))
            throw new Error(getMessage("m019"));
        else if (isObservableObject(value)) {
            var o = value.$mobx;
            return o.values && !!o.values[property];
        }
        return false;
    }
    return isObservableObject(value) || !!value.$mobx || isAtom(value) || isReaction(value) || isComputedValue(value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isObservableArray"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservableArray (thing)](#apidoc.element.mobx.mobx_umd.isObservableArray)
- description and source-code
```javascript
function isObservableArray(thing) {
    return isObject(thing) && isObservableArrayAdministration(thing.$mobx);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isObservableMap"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservableMap (x)](#apidoc.element.mobx.mobx_umd.isObservableMap)
- description and source-code
```javascript
isObservableMap = function (x) {
    return isObject(x) && x[propName] === true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isObservableObject"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isObservableObject (thing)](#apidoc.element.mobx.mobx_umd.isObservableObject)
- description and source-code
```javascript
function isObservableObject(thing) {
    if (isObject(thing)) {
        runLazyInitializers(thing);
        return isObservableObjectAdministration(thing.$mobx);
    }
    return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.isStrictModeEnabled"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>isStrictModeEnabled ()](#apidoc.element.mobx.mobx_umd.isStrictModeEnabled)
- description and source-code
```javascript
function isStrictModeEnabled() {
    return globalState.strictMode;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.map"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>map (initialValues)](#apidoc.element.mobx.mobx_umd.map)
- description and source-code
```javascript
function map(initialValues) {
    deprecated("'mobx.map' is deprecated, use 'new ObservableMap' or 'mobx.observable.map' instead");
    return observable.map(initialValues);
}
```
- example usage
```shell
...
import {observer} from 'mobx-react';

@observer
class TodoListView extends Component {
    render() {
        return <div>
            <ul>
                {this.props.todoList.todos.map(todo =>
                    <TodoView todo={todo} key={todo.id} />
                )}
            </ul>
            Tasks left: {this.props.todoList.unfinishedTodoCount}
        </div>
    }
}
...
```

#### <a name="apidoc.element.mobx.mobx_umd.observable"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>observable (v)](#apidoc.element.mobx.mobx_umd.observable)
- description and source-code
```javascript
function createObservable(v) {
    if (v === void 0) { v = undefined; }
    if (typeof arguments[1] === "string")
        return deepDecorator.apply(null, arguments);
    invariant(arguments.length <= 1, getMessage("m021"));
    invariant(!isModifierDescriptor(v), getMessage("m020"));
    if (isObservable(v))
        return v;
    var res = deepEnhancer(v, undefined, undefined);
    if (res !== v)
        return res;
    return observable.box(v);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.observe"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>observe (thing, propOrCb, cbOrFire, fireImmediately)](#apidoc.element.mobx.mobx_umd.observe)
- description and source-code
```javascript
function observe(thing, propOrCb, cbOrFire, fireImmediately) {
    if (typeof cbOrFire === "function")
        return observeObservableProperty(thing, propOrCb, cbOrFire, fireImmediately);
    else
        return observeObservable(thing, propOrCb, cbOrFire);
}
```
- example usage
```shell
...
if (typeof cbOrFire === "function")
    return observeObservableProperty(thing, propOrCb, cbOrFire, fireImmediately);
else
    return observeObservable(thing, propOrCb, cbOrFire);
}
exports.observe = observe;
function observeObservable(thing, listener, fireImmediately) {
return getAdministration(thing).observe(listener, fireImmediately);
}
function observeObservableProperty(thing, property, listener, fireImmediately) {
return getAdministration(thing, property).observe(listener, fireImmediately);
}
function toJS(source, detectCycles, __alreadySeen) {
if (detectCycles === void 0) { detectCycles = true; }
if (__alreadySeen === void 0) { __alreadySeen = []; }
...
```

#### <a name="apidoc.element.mobx.mobx_umd.reaction"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>reaction (expression, effect, arg3)](#apidoc.element.mobx.mobx_umd.reaction)
- description and source-code
```javascript
function reaction(expression, effect, arg3) {
    if (arguments.length > 3) {
        fail(getMessage("m007"));
    }
    if (isModifierDescriptor(expression)) {
        fail(getMessage("m008"));
    }
    var opts;
    if (typeof arg3 === "object") {
        opts = arg3;
    }
    else {
        opts = {};
    }
    opts.name = opts.name || expression.name || effect.name || ("Reaction@" + getNextId());
    opts.fireImmediately = arg3 === true || opts.fireImmediately === true;
    opts.delay = opts.delay || 0;
    opts.compareStructural = opts.compareStructural || opts.struct || false;
    effect = action(opts.name, opts.context ? effect.bind(opts.context) : effect);
    if (opts.context) {
        expression = expression.bind(opts.context);
    }
    var firstTime = true;
    var isScheduled = false;
    var nextValue;
    var r = new Reaction(opts.name, function () {
        if (firstTime || opts.delay < 1) {
            reactionRunner();
        }
        else if (!isScheduled) {
            isScheduled = true;
            setTimeout(function () {
                isScheduled = false;
                reactionRunner();
            }, opts.delay);
        }
    });
    function reactionRunner() {
        if (r.isDisposed)
            return;
        var changed = false;
        r.track(function () {
            var v = expression(r);
            changed = valueDidChange(opts.compareStructural, nextValue, v);
            nextValue = v;
        });
        if (firstTime && opts.fireImmediately)
            effect(nextValue, r);
        if (!firstTime && changed === true)
            effect(nextValue, r);
        if (firstTime)
            firstTime = false;
    }
    r.schedule();
    return r.getDisposer();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.runInAction"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>runInAction (arg1, arg2, arg3)](#apidoc.element.mobx.mobx_umd.runInAction)
- description and source-code
```javascript
function runInAction(arg1, arg2, arg3) {
    var actionName = typeof arg1 === "string" ? arg1 : arg1.name || "<unnamed action>";
    var fn = typeof arg1 === "function" ? arg1 : arg2;
    var scope = typeof arg1 === "function" ? arg2 : arg3;
    invariant(typeof fn === "function", getMessage("m002"));
    invariant(fn.length === 0, getMessage("m003"));
    invariant(typeof actionName === "string" && actionName.length > 0, "actions should have valid names, got: '" + actionName + "'");
    return executeAction(actionName, fn, scope, undefined);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.spy"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>spy (listener)](#apidoc.element.mobx.mobx_umd.spy)
- description and source-code
```javascript
function spy(listener) {
    globalState.spyListeners.push(listener);
    return once(function () {
        var idx = globalState.spyListeners.indexOf(listener);
        if (idx !== -1)
            globalState.spyListeners.splice(idx, 1);
    });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.toJS"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>toJS (source, detectCycles, __alreadySeen)](#apidoc.element.mobx.mobx_umd.toJS)
- description and source-code
```javascript
function toJS(source, detectCycles, __alreadySeen) {
    if (detectCycles === void 0) { detectCycles = true; }
    if (__alreadySeen === void 0) { __alreadySeen = []; }
    function cache(value) {
        if (detectCycles)
            __alreadySeen.push([source, value]);
        return value;
    }
    if (isObservable(source)) {
        if (detectCycles && __alreadySeen === null)
            __alreadySeen = [];
        if (detectCycles && source !== null && typeof source === "object") {
            for (var i = 0, l = __alreadySeen.length; i < l; i++)
                if (__alreadySeen[i][0] === source)
                    return __alreadySeen[i][1];
        }
        if (isObservableArray(source)) {
            var res = cache([]);
            var toAdd = source.map(function (value) { return toJS(value, detectCycles, __alreadySeen); });
            res.length = toAdd.length;
            for (var i = 0, l = toAdd.length; i < l; i++)
                res[i] = toAdd[i];
            return res;
        }
        if (isObservableObject(source)) {
            var res = cache({});
            for (var key in source)
                res[key] = toJS(source[key], detectCycles, __alreadySeen);
            return res;
        }
        if (isObservableMap(source)) {
            var res_1 = cache({});
            source.forEach(function (value, key) { return res_1[key] = toJS(value, detectCycles, __alreadySeen); });
            return res_1;
        }
        if (isObservableValue(source))
            return toJS(source.get(), detectCycles, __alreadySeen);
    }
    return source;
}
```
- example usage
```shell
...
ObservableArray.prototype.replace = function (newItems) {
    return this.$mobx.spliceWithArray(0, this.$mobx.values.length, newItems);
};
ObservableArray.prototype.toJS = function () {
    return this.slice();
};
ObservableArray.prototype.toJSON = function () {
    return this.toJS();
};
ObservableArray.prototype.peek = function () {
    return this.$mobx.values;
};
ObservableArray.prototype.find = function (predicate, thisArg, fromIndex) {
    if (fromIndex === void 0) { fromIndex = 0; }
    this.$mobx.atom.reportObserved();
...
```

#### <a name="apidoc.element.mobx.mobx_umd.transaction"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>transaction (action, thisArg)](#apidoc.element.mobx.mobx_umd.transaction)
- description and source-code
```javascript
function transaction(action, thisArg) {
    if (thisArg === void 0) { thisArg = undefined; }
    deprecated(getMessage("m023"));
    return runInTransaction.apply(undefined, arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.untracked"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>untracked (action)](#apidoc.element.mobx.mobx_umd.untracked)
- description and source-code
```javascript
function untracked(action) {
    var prev = untrackedStart();
    var res = action();
    untrackedEnd(prev);
    return res;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.useStrict"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>useStrict (strict)](#apidoc.element.mobx.mobx_umd.useStrict)
- description and source-code
```javascript
function useStrict(strict) {
    invariant(globalState.trackingDerivation === null, getMessage("m028"));
    globalState.strictMode = strict;
    globalState.allowStateChanges = !strict;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.when"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>when (arg1, arg2, arg3, arg4)](#apidoc.element.mobx.mobx_umd.when)
- description and source-code
```javascript
function when(arg1, arg2, arg3, arg4) {
    var name, predicate, effect, scope;
    if (typeof arg1 === "string") {
        name = arg1;
        predicate = arg2;
        effect = arg3;
        scope = arg4;
    }
    else {
        name = ("When@" + getNextId());
        predicate = arg1;
        effect = arg2;
        scope = arg3;
    }
    var disposer = autorun(name, function (r) {
        if (predicate.call(scope)) {
            r.dispose();
            var prevUntracked = untrackedStart();
            effect.call(scope);
            untrackedEnd(prevUntracked);
        }
    });
    return disposer;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.mobx_umd.whyRun"></a>[function <span class="apidocSignatureSpan">mobx.mobx_umd.</span>whyRun (thing, prop)](#apidoc.element.mobx.mobx_umd.whyRun)
- description and source-code
```javascript
function whyRun(thing, prop) {
    switch (arguments.length) {
        case 0:
            thing = globalState.trackingDerivation;
            if (!thing)
                return log(getMessage("m024"));
            break;
        case 2:
            thing = getAtom(thing, prop);
            break;
    }
    thing = getAtom(thing);
    if (isComputedValue(thing))
        return log(thing.whyRun());
    else if (isReaction(thing))
        return log(thing.whyRun());
    return fail(getMessage("m025"));
}
```
- example usage
```shell
...
        break;
    case 2:
        thing = getAtom(thing, prop);
        break;
}
thing = getAtom(thing);
if (isComputedValue(thing))
    return log(thing.whyRun());
else if (isReaction(thing))
    return log(thing.whyRun());
return fail(getMessage("m025"));
}
exports.whyRun = whyRun;
function createAction(actionName, fn) {
invariant(typeof fn === "function", getMessage("m026"));
...
```



# <a name="apidoc.module.mobx.observable"></a>[module mobx.observable](#apidoc.module.mobx.observable)

#### <a name="apidoc.element.mobx.observable.observable"></a>[function <span class="apidocSignatureSpan">mobx.</span>observable (v)](#apidoc.element.mobx.observable.observable)
- description and source-code
```javascript
function createObservable(v) {
    if (v === void 0) { v = undefined; }
    if (typeof arguments[1] === "string")
        return deepDecorator.apply(null, arguments);
    invariant(arguments.length <= 1, getMessage("m021"));
    invariant(!isModifierDescriptor(v), getMessage("m020"));
    if (isObservable(v))
        return v;
    var res = deepEnhancer(v, undefined, undefined);
    if (res !== v)
        return res;
    return observable.box(v);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.observable.array"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>array (initialValues, name)](#apidoc.element.mobx.observable.array)
- description and source-code
```javascript
array = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("array");
    return new ObservableArray(initialValues, deepEnhancer, name);
}
```
- example usage
```shell
...
}
function deepEnhancer(v, _, name) {
    if (isModifierDescriptor(v))
        fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection
, not when modifying it");
    if (isObservable(v))
        return v;
    if (Array.isArray(v))
        return observable.array(v, name);
    if (isPlainObject(v))
        return observable.object(v, name);
    if (isES6Map(v))
        return observable.map(v, name);
    return v;
}
function shallowEnhancer(v, _, name) {
...
```

#### <a name="apidoc.element.mobx.observable.box"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>box (value, name)](#apidoc.element.mobx.observable.box)
- description and source-code
```javascript
box = function (value, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("box");
    return new ObservableValue(value, deepEnhancer, name);
}
```
- example usage
```shell
...
invariant(arguments.length <= 1, getMessage("m021"));
invariant(!isModifierDescriptor(v), getMessage("m020"));
if (isObservable(v))
    return v;
var res = deepEnhancer(v, undefined, undefined);
if (res !== v)
    return res;
return observable.box(v);
}
var IObservableFactories = (function () {
function IObservableFactories() {
}
IObservableFactories.prototype.box = function (value, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("box");
...
```

#### <a name="apidoc.element.mobx.observable.deep"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>deep ()](#apidoc.element.mobx.observable.deep)
- description and source-code
```javascript
deep = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepEnhancer, arguments[0]);
    }
    else {
        return deepDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.observable.map"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>map (initialValues, name)](#apidoc.element.mobx.observable.map)
- description and source-code
```javascript
map = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("map");
    return new ObservableMap(initialValues, deepEnhancer, name);
}
```
- example usage
```shell
...
import {observer} from 'mobx-react';

@observer
class TodoListView extends Component {
    render() {
        return <div>
            <ul>
                {this.props.todoList.todos.map(todo =>
                    <TodoView todo={todo} key={todo.id} />
                )}
            </ul>
            Tasks left: {this.props.todoList.unfinishedTodoCount}
        </div>
    }
}
...
```

#### <a name="apidoc.element.mobx.observable.object"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>object (props, name)](#apidoc.element.mobx.observable.object)
- description and source-code
```javascript
object = function (props, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("object");
    var res = {};
    asObservableObject(res, name);
    extendObservable(res, props);
    return res;
}
```
- example usage
```shell
...
if (isModifierDescriptor(v))
    fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection, not
 when modifying it");
if (isObservable(v))
    return v;
if (Array.isArray(v))
    return observable.array(v, name);
if (isPlainObject(v))
    return observable.object(v, name);
if (isES6Map(v))
    return observable.map(v, name);
return v;
}
function shallowEnhancer(v, _, name) {
if (isModifierDescriptor(v))
    fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection, not
 when modifying it");
...
```

#### <a name="apidoc.element.mobx.observable.ref"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>ref ()](#apidoc.element.mobx.observable.ref)
- description and source-code
```javascript
ref = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(referenceEnhancer, arguments[0]);
    }
    else {
        return refDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
    for (var i = 0, l = listeners.length; i < l; i++) {
        listeners[i](change);
    }
    untrackedEnd(prevU);
}
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
...
```

#### <a name="apidoc.element.mobx.observable.shallow"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>shallow ()](#apidoc.element.mobx.observable.shallow)
- description and source-code
```javascript
shallow = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(shallowEnhancer, arguments[0]);
    }
    else {
        return shallowDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
function asMap(data) {
    deprecated("asMap is deprecated, use observable.map or observable.shallowMap instead");
    return observable.map(data || {});
}
exports.asMap = asMap;
...
```

#### <a name="apidoc.element.mobx.observable.shallowArray"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>shallowArray (initialValues, name)](#apidoc.element.mobx.observable.shallowArray)
- description and source-code
```javascript
shallowArray = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowArray");
    return new ObservableArray(initialValues, referenceEnhancer, name);
}
```
- example usage
```shell
...
    if (isModifierDescriptor(v))
        fail("You tried to assign a modifier wrapped value to a collection, please define modifiers when creating the collection
, not when modifying it");
    if (v === undefined || v === null)
        return v;
    if (isObservableObject(v) || isObservableArray(v) || isObservableMap(v))
        return v;
    if (Array.isArray(v))
        return observable.shallowArray(v, name);
    if (isPlainObject(v))
        return observable.shallowObject(v, name);
    if (isES6Map(v))
        return observable.shallowMap(v, name);
    return fail("The shallow modifier / decorator can only used in combination with arrays, objects and maps");
}
function referenceEnhancer(newValue) {
...
```

#### <a name="apidoc.element.mobx.observable.shallowBox"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>shallowBox (value, name)](#apidoc.element.mobx.observable.shallowBox)
- description and source-code
```javascript
shallowBox = function (value, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowBox");
    return new ObservableValue(value, referenceEnhancer, name);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.mobx.observable.shallowMap"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>shallowMap (initialValues, name)](#apidoc.element.mobx.observable.shallowMap)
- description and source-code
```javascript
shallowMap = function (initialValues, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowMap");
    return new ObservableMap(initialValues, referenceEnhancer, name);
}
```
- example usage
```shell
...
if (isObservableObject(v) || isObservableArray(v) || isObservableMap(v))
    return v;
if (Array.isArray(v))
    return observable.shallowArray(v, name);
if (isPlainObject(v))
    return observable.shallowObject(v, name);
if (isES6Map(v))
    return observable.shallowMap(v, name);
return fail("The shallow modifier / decorator can only used in combination with arrays, objects and maps");
}
function referenceEnhancer(newValue) {
return newValue;
}
function deepStructEnhancer(v, oldValue, name) {
if (deepEqual(v, oldValue))
...
```

#### <a name="apidoc.element.mobx.observable.shallowObject"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>shallowObject (props, name)](#apidoc.element.mobx.observable.shallowObject)
- description and source-code
```javascript
shallowObject = function (props, name) {
    if (arguments.length > 2)
        incorrectlyUsedAsDecorator("shallowObject");
    var res = {};
    asObservableObject(res, name);
    extendShallowObservable(res, props);
    return res;
}
```
- example usage
```shell
...
    if (v === undefined || v === null)
        return v;
    if (isObservableObject(v) || isObservableArray(v) || isObservableMap(v))
        return v;
    if (Array.isArray(v))
        return observable.shallowArray(v, name);
    if (isPlainObject(v))
        return observable.shallowObject(v, name);
    if (isES6Map(v))
        return observable.shallowMap(v, name);
    return fail("The shallow modifier / decorator can only used in combination with arrays, objects and maps");
}
function referenceEnhancer(newValue) {
    return newValue;
}
...
```

#### <a name="apidoc.element.mobx.observable.struct"></a>[function <span class="apidocSignatureSpan">mobx.observable.</span>struct ()](#apidoc.element.mobx.observable.struct)
- description and source-code
```javascript
struct = function () {
    if (arguments.length < 2) {
        return createModifierDescriptor(deepStructEnhancer, arguments[0]);
    }
    else {
        return deepStructDecorator.apply(null, arguments);
    }
}
```
- example usage
```shell
...
function asReference(value) {
    deprecated("asReference is deprecated, use observable.ref instead");
    return observable.ref(value);
}
exports.asReference = asReference;
function asStructure(value) {
    deprecated("asStructure is deprecated. Use observable.struct, computed.struct or reaction options instead.");
    return observable.struct(value);
}
exports.asStructure = asStructure;
function asFlat(value) {
    deprecated("asFlat is deprecated, use observable.shallow instead");
    return observable.shallow(value);
}
exports.asFlat = asFlat;
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
