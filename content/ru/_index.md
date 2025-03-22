---
# Leave the homepage title empty to use the site title
title:
date: 2025-03-20
type: landing

sections:
  - block: hero
    content:
      title: |
        Рост дендритов
      image:
        filename: welcome.jpg
      text: |
        <br>
        
        Исследование математической модели роста дендритов.
  
  - block: collection
    content:
      title: Последние новости
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: post
    design:
      view: card
      columns: '1'
  
  - block: markdown
    content:
      title:
      subtitle: ''
      text:
    design:
      columns: '1'
      background:
        image: 
          filename: coders.jpg
          filters:
            brightness: 1
          parallax: false
          position: center
          size: cover
          text_color_light: true
      spacing:
        padding: ['20px', '0', '20px', '0']
      css_class: fullscreen
      
  - block: collection
    content:
      title: Последние публикации
      text: ""
      count: 5
      filters:
        folders:
          - publication
        publication_type: 'Project_stages'
    design:
      view: citation
      columns: '1'

  - block: markdown
    content:
      title:
      subtitle:
      text: |
        {{% cta cta_link="./people/" cta_text="Наша команда →" %}}
    design:
      columns: '1'
---
