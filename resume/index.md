---
layout: default
title: Resume
---

{% include nav.html %}

<style>
  .resume-switch { display: flex; gap: 8px; margin-bottom: 16px; }
  .resume-switch button { padding: 6px 12px; border: 1px solid #ccc; background: #f7f7f7; cursor: pointer; }
  .resume-switch button.active { background: #222; color: #fff; border-color: #222; }
  .resume-lang { display: none; }
  .resume-lang.active { display: block; }
</style>

<div class="resume-switch">
  <button type="button" data-lang="en" class="active">English</button>
  <button type="button" data-lang="de">Deutsch</button>
</div>

<div id="resume-en" class="resume-lang active">
{% capture en_md %}{% include_relative resume.en.md %}{% endcapture %}
{{ en_md | markdownify }}
</div>

<div id="resume-de" class="resume-lang">
{% capture de_md %}{% include_relative resume.de.md %}{% endcapture %}
{{ de_md | markdownify }}
</div>

<script>
  (function () {
    var buttons = document.querySelectorAll('.resume-switch button');
    function setLang(lang) {
      buttons.forEach(function (btn) {
        btn.classList.toggle('active', btn.getAttribute('data-lang') === lang);
      });
      document.getElementById('resume-en').classList.toggle('active', lang === 'en');
      document.getElementById('resume-de').classList.toggle('active', lang === 'de');
    }
    buttons.forEach(function (btn) {
      btn.addEventListener('click', function () {
        setLang(btn.getAttribute('data-lang'));
      });
    });
    setLang('en');
  })();
</script>
