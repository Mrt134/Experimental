This directory is designed to aid in testing custom .css stylesheets.
template.rst is a generic .rst file which will push all the formatted elements
through Sphinx for testing.

To change styles, several elements will have to be altered:
- conf.py
  - 'html_theme = <'trueos_style'>'
- custom theme folder added to 'themes' directory OR
- change name of themes/<trueos_style> directory
- Edit themes/trueos_style/theme.conf:
  - 'stylesheet = css/<trueos_style.css>'
- Rename themes/trueos_style/static/css/trueos_style.css
