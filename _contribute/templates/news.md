---
layout: wiki
title: News
description: "Template to use for news content"
parent: Templates
contributors: ['nonkerdoob'] 
---

# News

## Content

```markdown
(content)

# References
(reference links)
```

{: .highlight}
Unlike the template for Guides and WIki entries, news content doesn't use a ``# Title heading``. It is rather defined in the front matter

## Front Matter

```markdown
---
layout: post
title: News Title
description: "Description"
tags: ['tag'.'tag','tag']
image: https://image.url
contributors: ['github_username','github_username'] 
---
```

## Full template

```markdown
---
layout: post
title: News Title
description: "Description"
tags: ['tag'.'tag','tag']
image: https://image.url
contributors: ['github_username','github_username'] 
---

(content)

# References
(reference links)
```

## File naming

News content is published using the blogging feature Jekyll provides, hence they must be named in this format -

```
YEAR-MONTH-DAY-title.md
```

#### Sample
```
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```
