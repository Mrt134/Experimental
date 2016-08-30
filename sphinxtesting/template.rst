Level 1
*******

This document is meant to provide a generic framework for
testing custom .css formatting.

Level 2
=======

:numref:`Figure %s: Test Logo <trueoslogo>`

 TrueOS logo for testing.

.. _trueoslogo:

.. figure:: images/trueoslogo.png
   :scale: 100%

Level 3
---------

Directives:

:file:`testfile` with extra text for comparison.

:command:`testcommand` with extra text for comparison.

:kbd:`keystroke` with extra text for comparison.

:guilabel:`TestGuiLabel` with extra text for comparison.

:menuselection:`Click 1 --> Click 2` with extra text for comparison.

Experiment with monospace formats for file and command
directives.

.. note:: Testing formatting of notes.

.. tip:: Testing formatting of tips.

.. warning:: Testing formatting of warnings.

.. danger:: Testing formatting of danger tags.

Level 4
^^^^^^^

Testing special text characters and emphasis:

Testing **bold**.

Testing *italics*.

* Test list 1
* Test list 2
   
   * Test nesting list 1

* Test list 3

::

 Testing a code block.
 
 Creating a large box for testing.
 
Add additional themeing elements as they appear.

Warren's suggestions for themeing:

Blue link color is too light, low-contrast. 
trueos_style.css: 2076 - 2082: darkened with stronger blue.
added underline on hover.
Red clicked-link color is too light, low-contrast.
trueos_style.css: 2084 - 2086: darkened with strong red.
added underline on hover.

Borders on admonitions are too thick and too light.
note box: trueos_style.css 3859
tip box: 3867
warning box: 3855
danger box: 3850
Updated with new values:
border: 2px solid #8a8988;
border-radius: 5px

Main text in admonitions is light gray, low-contrast.
Add text colors to the lines used above ^
Add new value to above lines: color: #030303

Admonitions would look better with slightly radiused corners.
Added value to above lines: border-radius: 5px

Commands should use the same font typewriter font as filenames.
Already fixed - set to inconsolata: monospace + bolded.

.. TODO Filename background are somewhat distracting and reduce contrast.
   Maybe just use a different foreground color and no background?

.. TODO Remove either bold on menuselection, leave background color.

.. TODO Reduce height of menuselection boxes to same as guilabel,
   maybe reduce both, but make them the same.
   Same with :kbd:, reduce to same height as others.

.. TODO Can the "view page source" links be removed?

.. TODO Make figure captions normal size font.

.. TODO Make table titles and figure captions consistent?
   (Both on top or on bottom, left- or center-justified)
