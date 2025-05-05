## py-kms alternative front-end

### Backstory:
I came across a reddit post about it decided to test py-kms myself and to my suprise it is functional. however the webUI it provided lacks the design and burns my eyes out. so i decided to create this repository that holds Jinja2 template for py-kms. trust me pure HTML is not easy, hence i created this with comments to future me and to its contributors

### Features
- Clutterless Clients page
- Dark theme
- Modern CSS
- Dropdown Products page
- Copy to clipboard on GLVK
- Smooth Animation

### Docker
I highly suggest using [11note](https://github.com/11notes/docker-kms)'s image which uses this style as default.

```
name: "kms"
services:
  kms:
    image: "11notes/kms:stable"
    container_name: "kms"
    environment:
      TZ: "Europe/Zurich"
    volumes:
      - "var:/kms/var"
    ports:
      - "1688:1688/tcp"
    restart: "always"
  kms-gui:
    image: "11notes/kms-gui:stable"
    container_name: "kms-gui"
    environment:
      TZ: "Europe/Zurich"
    volumes:
      - "var:/kms/var"
    ports:
      - "8080:8080/tcp"
    restart: "always"
volumes:
  var:
```

### Screenshots
![{81958E47-9251-4A4B-B0DF-9484DEFFCD50}](https://github.com/user-attachments/assets/d55efd2a-07ba-42be-ae8f-cbe5b996bd9a)

![{7961AA36-E006-440B-957D-A34234DC71E9}](https://github.com/user-attachments/assets/67d43e62-cff8-4695-aa20-72920e0bdfd1)


# Libraries used
- [TailwindCSS](https://tailwindcss.com/)
- [jinja2](https://jinja.palletsprojects.com/)
