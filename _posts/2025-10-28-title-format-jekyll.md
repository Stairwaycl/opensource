---
layout: post
title: "EI wrote the title in the Front Matter in Jekyll, and it didn't work."
date: 2025-10-28 13:14:59 -0300
tag: jekyll
---

One of the most common mistakes when creating a new Jekyll post is a formatting failure in the top metadata block, known as the **Front Matter**.

### 🛠️ The Key Rule: Use Quotes for the Title

The **Front Matter** uses **YAML** (YAML Ain't Markup Language) syntax. YAML is sensitive to certain special characters (such as colons `:` or double quotes `"` within the title itself). To prevent YAML from interpreting your title as code rather than simple text, you **must** enclose the `title` property's value in double quotes.

#### ❌ Incorrect Syntax (Causes Processing Error)

Do not use the title without quotes, especially if it contains colons or is a complex phrase:

```yaml
---
layout: post
title: Error: The Title will not appear
date: 2025-10-28 13:14:59 -0300
---
```
#### ✅ Correct and Safe Syntax
Always include double quotes (") around your title text:

```yaml

---
layout: post
title: "Safe and Correct Title"
date: 2025-10-28 13:14:59 -0300
---
```

# Thanks for reading and visiting our site!
