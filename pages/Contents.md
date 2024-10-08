# Table of Contents
- [[Plot]]
- [[Characters]]
- [[Locations]]
- [[Historical Events]]
- [[Groups]]
- [[Scientific Concepts]]
- ---
- # Learning Queries
- #+BEGIN_QUERY
  {
  :title [:b "Groups with links"]
  :query [
    :find (pull ?block [*])
    :where
    (page-property ?block :story-role "group")
  ]
  :view (fn [vals]
    (for [d vals] (str "--" d "\n"))
   )
  }
  #+END_QUERY
- query-sort-by:: page
  query-sort-desc:: true
  query-properties:: [:page]
  #+BEGIN_QUERY
  {
  :title [:b "Groups"]
  :query [:find ?pagename
  :where
  [?block :block/original-name ?pagename]
  (page-property ?block :story-role "group")
  ]
  :result-transform (fn [result]
    (map (fn [r]
      (list 'link  (str r) (str r) ))
      result))
  :view :bullet
  }
  #+END_QUERY
-
- # External References
- https://en.wikipedia.org/wiki/The_Three-Body_Problem_(novel)
- https://www.gradesaver.com/the-three-body-problem