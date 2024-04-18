---
layout: workshop      # Цей текст не можна змінювати.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "FIXME"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "FIXME"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "FIXME"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "FIXME"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "45"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-1"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "FIXME"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "FIXME"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: FIXME      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: FIXME        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["instructor one", "instructor two"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["helper one", "helper two"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["first@example.org","second@example.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}


{% comment %}
8< ============= For a workshop delete from here =============
For a workshop please delete the following block until the next dashed-line
{% endcomment %}


<div class="alert alert-danger">
Це шаблон для сторінки семінару. Видаліть ці рядки і використайте його для налаштування свого семінару (інструкція англійською знаходяться
<a href="https://carpentries.github.io/workshop-template/customization/index.html">тут</a>).
Якщо ви проводите цей семінар самостійно або ще не відправили запит на семінар, будь-ласка заповніть
<a href="{{site.amy_site}}/forms/self-organised/">цю форму</a>
щоб повідомити нас про ваш семінар, і ми зв'яжемось з вами, якщо нам буде потрібна додаткова інформація.
Якщо це перший семінар для нового уроку,
вкажіть значення `true` в полі `pilot` у файлі `_config.yml`.
Для семінарів, які викладають уроки з Carpentries Incubator,
треба видалити коментарі з полей `incubator_lesson_site`, `incubator_pre_survey`, та `incubator_post_survey`
у файлі `_config.yml`.
</div>

{% comment %}
8< ============================= until here ==================
{% endcomment %}


{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" %}
{% unless site.curriculum == "dc-astronomy" or site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-geospatial" or site.curriculum == "dc-image" or site.curriculum == "dc-socsci" %}
<div class="alert alert-warning">
Схоже, що ви налаштовуєте веб-сайт для навчальної програми Data Carpenterry, але ви не вказали тип навчальної програми у файлі <code>_config.yml</code> (поточне значення у <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", можливі значення: <code>dc-image</code>, <code>dc-astronomy</code>, <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). Після редагування цього файлу вам потрібно знову запустити <code>make serve</code> , щоб побачити відображені зміни.
</div>
{% endunless %}
{% endif %}

{% comment %}
Перевірте навчальний план SWC
{% endcomment %}

{% if site.carpentry == "swc" %}
{% unless site.curriculum == "swc-inflammation" or site.curriculum == "swc-gapminder" %}
<div class="alert alert-warning">
Схоже, ви налаштовуєте веб-сайт для навчального плану Software Carpentry, але не вказали тип навчального плану у файлі <code>_config.yml</code> (поточне значення у <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>swc-inflammation</code>, or <code>swc-gapminder</code>). Після редагування цього файлу вам потрібно знову запустити <code>make serve</code>, щоб побачити відображені зміни.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

Цей блок містить віджет реєстрації Eventbrite, якщо в заголовку встановлено «eventbrite». Ви можете видалити його, якщо ви не використовуєте Eventbrite, або залишити його, оскільки воно не відображатиметься, якщо поле 'eventbrite' у заголовку не встановлено.
{% endcomment %}
{% if page.eventbrite %}
<strong>Деякі блокувальники реклами блокують вікно реєстрації. Якщо ви не бачите поле реєстрації нижче, перевірте налаштування блокувальника реклами.</strong>
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
ВСТУП

Відредагуйте загальний пояснювальний абзац нижче, якщо ви хочете змінити "pitch"
{% endcomment %}

<p>
<strong><a href="https://carpentries.org">Проект Carpentries</a></strong> містить в собі<a
href="{{site.swc_site}}">Software Carpentry</a>, <a href="{{site.dc_site}}">Data Carpentry</a>, та
<a href="{{site.lc_site}}">Library Carpentry</a> спільноти інструкторів, тренерів, супроводжувачів, помічників і прихильників, які мають спільну місію — навчати дослідників основним навичкам обчислення та науки про дані.
<p align="center">
  <em>
  <strong>Хочете дізнатися більше та підтримувати співпрацю з Carpentries?</strong> Carpentries Clippings — це двотижневий інформаційний вісник The Carpentries, де ми ділимося новинами спільноти, оголошеннями про вакансії тощо.
Зареєструйтеся, щоб отримувати наступні видання та читати наш повний архів: <a href="https://carpentries.org/newsletter/">https://carpentries.org/newsletter/</a>
  </em>
</p>
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% if site.pilot %}
Це пілотний семінар, де проходить тестування уроку, який ще розробляється. Автори уроку будуть вдячні за будь-які відгуки, які ви можете надати їм щодо змісту уроку та пропозиції щодо його подальшого вдосконалення.
{% endif %}

{% comment %}
АУДИТОРІЯ

Поясніть, хто ваша аудиторія.  (Зокрема, повідомте аудиторії, чи семінар відкритий лише для людей з певної установи.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
МІСЦЕЗНАХОДЖЕННЯ

У цьому блоці відображається адреса та посилання на карти, що показують напрямки, якщо було встановлено широту та довготу семінару. Ви можете використовувати https://www.latlong.net/, щоб знайти широту/довготу
адресу.
{% endcomment %}
{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if page.latitude and page.longitude and online == "false" %}
<p id="where">
  <strong>Де:</strong>
  {{page.address}}.
  Отримати напрямок за допомогою
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  або
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% elsif online == "true_public" %}
<p id="where">
  <strong>Де:</strong>
  онлайн за адресою <a href="{{page.address}}">{{page.address}}</a>.
  Якщо вам потрібен пароль або інша інформація для доступу до тренінгу, інструктор дасть його вам перед семінаром.
</p>
{% elsif online == "true_private" %}
<p id="where">
  <strong>Де:</strong> Цей семінар відбуватиметься онлайн.
  Інструктори нададуть вам інформацію, яка вам знадобиться для того щоб приєднатися до цієї зустрічі.
</p>
{% endif %}

{% comment %}
ДАТА

Цей блок відображає дату та посилання на Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
ОСОБЛИВІ ВИМОГИ

Змініть блок нижче, якщо є якійсь особливі вимоги.
{% endcomment %}
<p id="requirements">
  <strong>Вимоги:</strong>
  {% if online == "false" %}
    Слухачі повинні мати з собою ноутбук з операційною системою Mac, Linux або Windows (не планшет, Chromebook тощо), на якому вони мають права адміністратора.
  {% else %}
    Слухачі повинні мати доступ до комп’ютера з операційною системою Mac, Linux або Windows (не планшет, Chromebook тощо), на якому вони мають права адміністратора.
  {% endif %}
  У них має бути встановлено декілька спеціальних програмних пакетів (перелічених тут <a href="#setup">below</a>).
</p>

{% comment %}
ДОСТУПНІСТЬ

Змініть блок нижче, якщо є будь-які перешкоди для доступності або спеціальні інструкції.
{% endcomment %}
<p id="accessibility">
  <strong>Доступність:</strong>
{% if online == "false" %}
  Ми прагнемо зробити цей семінар зручним для всіх. Для семінарів у фізичному місці організатори семінарів переконалися, що:
</p>
<ul>
  <li>Приміщення пристосоване для інвалідних візків/самокатів.</li>
  <li>Є доступні вбиральні.</li>
</ul>
<p>
  Матеріали будуть надані до початку семінару, а матеріали великим шрифтом для видачі будуть доступні за потреби, попередньо повідомивши про це організаторів. Якщо ми можемо допомогти вам полегшити навчання (наприклад, сурдоперекладачі, приміщення для лактації), будь ласка, зв'яжіться з нами (використовуючи контактні дані нижче), і ми спробуємо їх надати.
</p>
{% else %}
  Ми прагнемо створити позитивне та доступне навчальне середовище для всіх.
  Ми не вимагаємо від учасників надавати документи про інвалідність або розкривати будь-яку непотрібну особисту інформацію.
  Однак ми хочемо допомогти створити інклюзивний, доступний досвід для всіх учасників.
  Ми заохочуємо вас поділитися будь-якою інформацією, яка може бути корисною для того, щоб зробити ваш досвід в Carpentries більш доступним.
  Щоб запросити житло для цього семінару, будь ласка, заповніть
  <a href="https://carpentries.typeform.com/to/B2OSYaD0">форму запиту на проживання</a>.
  Якщо у вас є запитання або вам потрібна допомога з реєстрацією на житло, <a href="mailto:team@carpentries.org">напишіть нам електронною поштою</a>.
</p>
{% endif %}

{% comment %}
КОНТАКТНА АДРЕСА ЕЛЕКТРОННОЇ ПОШТИ

Відобразити контактну адресу електронної пошти, які вказана у файлі конфігурації.
{% endcomment %}
<p id="contact">
  <strong>Контакт:</strong>
  Будь ласка, напишіть
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  або
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<p id="roles">
  <strong>Ролі:</strong>
  Щоб дізнатися більше про ролі на семінарі (хто що робитиме), зверніться до нашої платформи Workshop FAQ<a href="https://carpentries.org/workshop_faq/#what-are-the-roles-of-everyone-participating-in-a-workshop"> </a>.
</p>

{% comment %}
ХТО МОЖЕ БРАТИ УЧАСТЬ?

Якщо ви хочете вказати, хто може відвідати семінар, ви можете скористатися розділом нижче.

Перемістіть тег 'endcomment' над початком наступного
<p> тегу, щоб зробити цей розділ видимим.

Відредагуйте текст відповідно до того, хто може відвідувати семінар. Наприклад:
- Цей семінар відкритий для осіб у партнерських выдносинах з університетом ABC.
- Цей семінар відкритий для громадськості.
- Якщо ви зацікавлені в відвідуванні цього семінару, напишіть на me@example.com для отримання подальшої інформації

<p id="who-can-attend">
    <strong>Who can attend?:</strong>
    This workshop is open to ....
</p>
{% endcomment %}

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
  <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
    <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
  </a>
</p>
<hr/>


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD)
available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}


{% comment %}
SURVEYS - DO NOT EDIT SURVEY LINKS
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "incubator" %}
<p><a href="{{ site.incubator_pre_survey }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.incubator_post_survey }}">Post-workshop Survey</a></p>
{% elsif site.incubator_pre_survey or site.incubator_post_survey %}
<div class="alert alert-danger">
WARNING: you have defined custom pre- and/or post-survey links for
a workshop not configured for The Carpentries Incubator
(the value of `curriculum` is not set to `incubator` in `_config.yml`).
Please comment out the `incubator_pre_survey` and `incubator_post_survey` fields
in `_config.yml` or, if this workshop is teaching a lesson in the Incubator,
change the value of `carpentry` to `incubator`.
</div>
{% else %}
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.

Small changes to the schedule can be made by modifying the
`schedule.html` found in the `_includes` folder for your
workshop type (`swc`, `lc`, or `dc`). Edit the items and
times in the table to match your plans. You may also want to
change 'Day 1' and 'Day 2' to be actual dates or days of the
week.

For larger changes, a blank template for a 4-day workshop
(useful for online teaching for instance) can be found in
`_includes/custom-schedule.html`. Add the times, and what
you will be teaching to this file. You may also want to add
rows to the table if you wish to break down the schedule
further. To use this custom schedule here, replace the block
of code below the Schedule `<h2>` header below with
`{% include custom-schedule.html %}`.
{% endcomment %}

<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% elsif site.carpentry == "incubator" %}
This workshop is teaching a lesson in [The Carpentries Incubator](https://carpentries-incubator.org/).
Please check [the lesson homepage]({{ site.incubator_lesson_site }}) for a list of lesson sections and estimated timings.
{% endif %}

{% comment %}
Edit/replace the text above if you want to include a schedule table.
See the contents of the _includes/custom-schedule.html file for an example of
how one of these schedule tables is constructed.
{% endcomment %}

{% if site.pilot %}
The lesson taught in this workshop is being piloted and a precise schedule is yet to be established. The workshop will include regular breaks. Please [contact the workshop organisers](#contact) if you would like more information about the planned schedule.
{% endif %}

<hr/>


{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to software as described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% comment %}
For online workshops, the section below provides:
- installation instructions for the Zoom client
- recommendations for setting up Learners' workspace so they can follow along
  the instructions and the videoconferencing

If you do not use Zoom for your online workshop, edit the file
`_includes/install_instructions/videoconferencing.html`
to include the relevant installation instructions.
{% endcomment %}
{% if online != "false" %}
{% include install_instructions/videoconferencing.html %}
{% endif %}

{% comment %}
These are the installation instructions for the tools used
during the workshop.
{% endcomment %}

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% elsif site.carpentry == "incubator" %}
Please check the "Setup" page of
[the lesson site]({{ site.incubator_lesson_site }}) for instructions to follow
to obtain the software and data you will need to follow the lesson.
{% endif %}
