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
Unlike the template for Guides and WIki entries, news content doesn't use a title heading. It is defined in the front matter

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
