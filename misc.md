# Miscellaneous Notes

## `doseq`, `dorun`, `doall`

* **`doall`**
    
    `doall` forces the evaluation of the lazy sequence and it retains the head, causing the entire seq to live in memory. Useful when you want to immediately force evaluation of something like `map`. I use the "all" part of `doall` to help me remember that it keeps all the items of the seq in memory.

* **`dorun`**
    
    Use `dorun` when you just want the side effects of computing the lazy sequence, but you don’t care about the items in the sequence itself. But be careful when you see yourself using `(dorun (map ... ))`, you should probably use doseq instead. I use the "run" part of `dorun` to help me remember that it only runs over the seq for side effects, without keeping anything.

* **`doseq`**

    To me `doseq` has more in common with `for` than with `doall` or `dorun`. Since in Clojure for is used for lazy list-comprehension, `doseq` fulfills the role of something like "`for ... in ...`" or "`foreach`" from other languages. It takes the same arguments that `for` does, but it runs immediately and it doesn’t collect the results. I really feel that `doseq` needs a better name so I don’t have a good way to remember what it does just by looking at its name.

### See Also

* [Difference between doseq and for in Clojure](https://stackoverflow.com/questions/4725417/difference-between-doseq-and-for-in-clojure)
* [What is the difference among the functions `doall`, `dorun`, `doseq`, and `for`?](https://stackoverflow.com/questions/25327369/what-is-the-difference-among-the-functions-doall-dorun-doseq-and-for)
