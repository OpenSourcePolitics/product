# Term Customizer – revamp suggestion

The `term_customizer` module lets admins change words across the platform without editing code. 

## Goals of the revamp

- Make it easier to find and change any word on the platform
- Make sure changes always show up everywhere
- Make the interface easier to understand and use

---

## 1. Search problems

### 🔍 Can’t find terms reliably

#### Problem
Typing part of a word sometimes shows nothing. Sometimes results disappear after you click on one. Search is quite unreliable.

![image](https://github.com/user-attachments/assets/c492eb7d-f59c-4ad1-859f-7b2131b247d0)

#### Goals
- Improve search to handle partial matches, fuzzy matches, and typos
- Make all translation keys searchable

### 🔗 Can’t tell where a word appears

#### Problem
Some words are used in multiple locations on the site. Admins don’t know where a term they selected is used on the site. That makes it hard to check what they’re changing.

Example of the same word in two separate keys : 
![image](https://github.com/user-attachments/assets/909c4760-baf8-4444-b21a-c34b7262f0c4)


#### Fix
- List all the pages on which a term is used (when you select to show this)
- Let admins paste a URL from a page on their Decidim and give back a list of all terms used on that page and make it possible for the admin to select among them 

### 📦 No quick way to rename a group of terms

#### Problem
Many admins want to rename things like “Proposals” everywhere, but have to find all the keys related to the term manually.

#### Fix
- Add presets of term modifications for a common sets of terms (e.g. “Proposals”)

---

## 2. Translation doesn’t always work

### ⏱️ Changes don’t show up right away

#### Problem
Admins add a new term, but it doesn’t appear right away. Sometimes they have to refresh multiple times or clear the cache.

#### Goal
- Automatically clear the right cache when a translation is saved
- Make sure the change appears everywhere immediately

### 🔁 Some terms change, others don’t

#### Problem
Sometimes a term is changed but still appears in its original form in some parts of the platform.

---

## 3. Interface is confusing

### ❓ Icons are unclear

#### Problem
The UI uses icons (like the “eye” and “pencil”) that are hard to understand. Some are used incorrectly.

![image](https://github.com/user-attachments/assets/221e1c52-a823-40e4-8f91-b3bba156cf6f)

#### Fix
- Only keep the "Eye" button that redirects inside the translation set
- At the top of the translation set view add a "Configuration" part that would redirect to the set's configuration page previously under the "Pencil" icon
- Replace duplicate icon with an appropriate one such as this : file-copy-line (Remix icon)

### ♻️ Manual cache clearing is annoying

#### Problem
Admins have to click a button to clear the cache every time they make a change.

#### Fix
- Clear the cache automatically when saving a new term or modifying a term

### 🔁 Two ways to add terms (and one of them isn't useful)

#### Problem
There are two ways to add new translations. One of them doesn’t even have search, so people rarely use it.

#### Fix
- Keep just one “add translation” method (ideally the one that's currently called "Add multiple")
- Make sure it supports search 
