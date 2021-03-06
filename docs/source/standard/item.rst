.. . Kicking page rebuild 2014-10-30 17:00:08
.. include:: defs.hrst

.. index:: Item, Parameter, Classification, CAV, Unit

.. _Item:

Item
====

Schema
------

:id:
    string, auto-generated, required

:description:
    string, multilingual, required

    |ocdsDescription|
    A description of the goods, services to be provided.
    
    Brief description of property (for ``dgfOtherAssets``) or asset(s) (for ``dgfFinancialAssets``).
    
:classification:
    :ref:`Classification`, required

    |ocdsDescription|
    The primary classification for the item. See the
    `itemClassificationScheme` to identify preferred classification lists.

    It is required for `classification.scheme` to be `CPV` or `CAV-PS`. The
    `classification.id` should be valid `CPV` or `CAV-PS` code.

:additionalClassifications:
   Array of :ref:`Classification` objects, optional

    |ocdsDescription|
    An array of additional classifications for the item. See the
    `itemClassificationScheme` codelist for common options to use in OCDS. 
    This may also be used to present codes from an internal classification
    scheme.

:unit:
    :ref:`Unit`, required

    |ocdsDescription| 
    Description of the unit which the good comes in e.g.  hours, kilograms. 
    Made up of a unit name, and the value of a single unit.

:quantity:
    decimal, required

    |ocdsDescription|
    The number of units required

:address:
    :ref:`Address`, required

    Address, where property (for ``dgfOtherAssets``) or asset(s) (for ``dgfFinancialAssets``) is located.

:location:
    dictionary, optional

    Geographical coordinates of the location. Element consists of the following items:

    :latitude:
        string, required
    :longitude:
        string, required
    :elevation:
        string, optional, usually not used

    `location` usually takes precedence over `address` if both are present.

.. _Classification:

Classification
==============

Schema
------

:scheme:
    string, required

    |ocdsDescription|
    A classification should be drawn from an existing scheme or list of
    codes.  This field is used to indicate the scheme/codelist from which
    the classification is drawn.  For line item classifications, this value
    should represent a known Item Classification Scheme wherever possible.

:id:
    string, required

    |ocdsDescription|
    The classification code drawn from the selected scheme.

:description:
    string, required

    |ocdsDescription|
    A textual description or title for the code.

:uri:
    uri, optional

    |ocdsDescription|
    A URI to identify the code. In the event individual URIs are not
    available for items in the identifier scheme this value should be left
    blank.

.. _Unit:

Unit
====

Schema
------

:code:
    string, required

    UN/CEFACT Recommendation 20 unit code.

:name:
    string

    |ocdsDescription|
    Name of the unit
