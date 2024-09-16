# Table of Contents
- [[Plot]]
- [[Characters]]
- [[Groups]]
- #+BEGIN_QUERY
  {
  :title [:b "Groups with links"]
  :query [
    :find :block/*
    :where (page-property ?block :story-role "group")
  ]
  }
  #+END_QUERY
-
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
  :view :inline
  }
  #+END_QUERY
- [[Locations]]
- [[Scientific Concepts]]
- [[Historical Events]]
- # External References
- https://en.wikipedia.org/wiki/The_Three-Body_Problem_(novel)
- https://www.gradesaver.com/the-three-body-problem