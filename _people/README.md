# README

To add a person create a new file (format does not matter but suggest using an identifier like their name). The YAML front matter then contains information currently utilized by the publications page. The `pub_id` should match what the person's reference looks like (e.g. "M Sonnewald" for Maike Sonnewald using `nature.cls`).

Required Keywords:
- `lastname`: Last name
- `firstname`: First name
- `pub_id`: String to identify person in the bibliography
- `role`: Person's role in the group listed in the People page
- `status`: *active* or *alumn*
- `sort_display`: order to display person on the People page (highers to lowest)
- `image_path`: Person's image. Should be square. Can use otter image.

Optional Keywords:
- `website`: Linked to name on the People page
- `pronouns`

Example:
```
---
lastname: "Sonnewald"
firstname: "Maike"
pub_id: "Sonnewald M"
role: "Group Leader"
status: "active"
pronouns: "she/her"
sort_display: 4
image_path: /assets/images/profile-maike.jpg
website: "https://www.msonnewald.com/"
---
```