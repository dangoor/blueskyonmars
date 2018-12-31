---
title: TurboGears 0.9a2 released!
author: Kevin Dangoor
type: post
date: 2006-03-27T23:04:51+00:00
url: /2006/03/27/turbogears-09a2-released/
categories:
  - Python
  - TurboGears

---
I&#8217;m happy to report that [TurboGears][1] 0.9a2 has been released! We&#8217;ve had a whole raftload of feedback and contributions since the release of 0.9a1. 0.9 is becoming considerably more solid, but I&#8217;m not going to upgrade it to &#8220;beta&#8221; until there are more docs. Be sure to read the [upgrade instructions][2], because you&#8217;ll need to make some changes to come from 0.9a1 or 0.8 to this release.
  
[TurboGears Changelog][3]

_Backwards Incompatibilities_

  * Due to Python 2.3 issues and some additional discussion, the config files have gone back to an INI-style format. This means that some minor changes are needed if you were using the 0.9 â€œ.pyâ€? config files, but no changes are required for people using 0.8 â€œ.cfgâ€? config files. See the upgrading guide for details.
  * If you used CompoundWidgets in 0.9a1, â€œwidgetsâ€? has changed to â€œmember_widgetsâ€?.
  * If you are using a Form or a FieldSet widget you must explicitly pass the â€œfieldsâ€? parameter, the first positional parameter expected since 0.9a2 is â€œnameâ€?.
  * If you are using a Form or a FieldSet widget with a custom template you must update your template accordingly to the new templates TG is using.

_Deprecations_

  * WidgetsDeclaration (introduced in 0.9a1) has been renamed WidgetsList for clarity.
  * turbogears.config now has get() and update() functions that should be used in place of their cherrypy.config counterparts. This change was made knowing that there will be more powerful, TurboGears-specific configuration in TurboGears 1.1.
  * The field\_for method of a Form (introduced in 0.9a1) has been deprecated and itâ€™s use is highly discouraged and error prone, use display\_field\_for or render\_field_for instead.
  * In the turbogears.view module variableProviders has been renamed variable_providers.
  * turbogears.fastdata.formmakerâ€™s sqlwidgets function (introduced in 0.9a1) has been renamed fields_for.

_New Features_

  * Controller methods can now have multiple expose() decorators, allowing you to define different output formats (even with different template engines) that can be chosen via tg_format or the Accept header.
  * New AjaxGrid widget provides a grid in JavaScript that is populated via an Ajax call.
  * Three new base widgets to manage forms have been introduced: CompoundFormField, RepeatingFormField and FormFieldsContainer.
  * Experimental support for SQLAlchemy. For more complicated databases or certain database requirements, SQLAlchemy handles the database more gracefully. The main database layer for TurboGears remains SQLObject and SQLObject is more fully supported within TurboGears. However, for those who need it, SQLAlchemy support is there.
  * display\_field\_for and render\_field\_for are automatically added to the template scope of any FormFieldsContainer widget and can be used to easily display/render a field with the corrects value and options.
  * The basis for creating repeating sets of widgets has been created (see RepeatingFormField and RepeatingFieldSet for an example)
  * Catwalk can filter the data you see
  * When using widgets, you can now have more than one form on a page while retaining validation sanity.
  * With widgets, required fields automatically get a CSS class
  * CompoundWidgets/Forms now use FormEncode schemas, which provide a number of additional validation options.
  * AutoCompleteFields can now pass an ID back to the server when submitted (instead of just passing the matching search string).
  * quickstart includes a â€œrelease.pyâ€? file where you can put your project information (including version number). This is the safe mechanism for allowing your project itself to access the version number while your setup script also has access to the same information (Donâ€™t Repeat Yourself)
  * quickstart has a new â€œtgbigâ€? template designed for larger projects. This adds a controllers package to the basic TurboGears template.
  * CSSLink and CSSSource widgets now support â€œmediaâ€?
  * The AutoCompleteField now has an â€œonly_suggestâ€? flag which makes it so that the first item on the list is not automatically submitted when you press return. This is useful for search boxes (as opposed to data entry fields).
  * The turbogears.startup now contains call_on_startup and call_on_shutdown lists. You can append callables to these to have them executed at the right time.
  * If you are using the i18n support, the _ function (alias of the gettext function) is now properly mapped to lazy_gettext if needed, this means you can use â€œ_â€? for everything.
  * Added LocalizableJSLink widget that allows scripts to be chosen based on the userâ€™s locale.

_Changes_

  * log\_debug\_info_filter is now turned off by default (this is the CherryPy filter that lists the request time). This filter causes problems with things like JSON output. You can still turn it back on via the config file.
  * Unless you specifically configure the decodingFilter yourself, TurboGears will automatically turn on CherryPyâ€™s decodingFilter (expecting utf-8 input).
  * cherrypy.lowercase_api is set to True in new quickstarted projects. This should result in a performance boost, and requires that you use PEP 8 style names when calling CherryPy APIs/config values.
  * Table forms now use TH tags for the field labels, making it easier to apply appropriate styling to the tables.
  * AutoConnectHub used to support a â€œprocessConnectionâ€? (something it inherited from SQLObject). This is not really a supported model of operation, so it has been removed. If you do want to work that way, use SQLObjectâ€™s own ConnectionHub class.
  * The test_model test has been commented out from the quickstart template, because some projects donâ€™t have databases.

_Fixes_

  * The TextArea widget now posts properly within a RemoteForm.
  * Catwalk styling cleanup
  * Catwalk no longer has problems with empty tables with foreign keys
  * ForEach validator added to turbogears.validators namespace
  * Catwalk will show related joins in the edit view
  * SQLObject identity provider passwords are automatically encrypted (this was in 0.9a1). This didnâ€™t work properly when identity wasnâ€™t fully running (as in the tg-admin shell). This has been fixed.
  * The AutoCompleteField turns off the browserâ€™s own autocompletion.
  * A nicer error message is provided if you return something other than a string or a dict from your controller method.
  * admi18n does a better job of grouping files in the correct folder when collecting strings and skips over folders like â€œ.svnâ€?.
  * The turbogears.url() function was flipping around path elements in the application root. Applications roots are not commonly used right now, but this was noticeable if you used the FeedController.
  * Various fixes for CatWalkâ€™s database access (see tickets #568, #249, #213, #618)
  * ModelDesigner and admi18n can find your model.py file even if you change your package name at quickstart time.

_Project Updates_

  * Kid 0.9 / TurboKid 0.9.2
  * CherryPy 2.2.0rc1
  * PasteScript 0.5
  * TurboGearsâ€™ JSON output now comes from the TurboJson plugin

_Contributors_

This release comes to you thanks to the work of Michele Cella, Elvelind Grandin, Ronald Jaramillo, Simon Belak, Jeff Watkins, Alberto Valverde GonzÃ¡lez, Jason Chu, Owen Mead-Robins, Dan Weeks, Dennis Brakhane, Heikichi Umahara, Patrick Lewis, Joost Moesker, Roger Demetrescu, Liza Daly.

 [1]: http://www.turbogears.org/preview/
 [2]: http://www.turbogears.org/preview/download/upgrade.html
 [3]: http://www.turbogears.org/preview/about/changelog.html