# cljs-uuid

Simple CLJS uuid generator

* can generate version4 (random uuid), as per http://www.ietf.org/rfc/rfc4122.txt
* can read and print uuid literals as per http://dev.clojure.org/jira/browse/CLJ-914
* can read and print plain uuid strings '8-4-4-4-12'

## usage

* clojars [cljs-uuid "0.0.1"]


'''clojure
(ns cljs.main
  (:require
    [cljs-uuid.core :as uuid]
    )
  )

; make a uuid
(def u (uuid/make-v4))

; as a string
(str u)

; read a uuid string 
(def u2 (uuid/read-str "7ec23197-d016-40e4-a03a-145fe85bfd8f"))

; as clj reader literal
(pr-str u)

; read a uuid pr-str string 
(def u3 (uuid/read-pr-str "#uuid 7ec23197-d016-40e4-a03a-145fe85bfd8f"))

; equality works
(= u2 u3)
'''

## TODO

consider use of 'window.crypto.getRandomValues' when available


## License

Copyright (C) 2012 Dave Sann

Distributed under the Eclipse Public License, the same as Clojure.