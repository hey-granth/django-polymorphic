.. _advanced-features:

Advanced Features
=================

In the examples below, these models are being used:

.. literalinclude:: ../src/polymorphic/tests/examples/advanced/models.py
   :caption: src/polymorphic/tests/examples/advanced/models.py
   :language: python
   :lines: 1-17
   :linenos:

Filtering for classes (equivalent to python's :func:`isinstance`)
------------------------------------------------------------------

.. literalinclude:: ../src/polymorphic/tests/examples/advanced/tests.py
   :caption: src/polymorphic/tests/examples/advanced/tests.py (instance_of + Q)
   :language: python
   :pyobject: AdvancedExamplesTests.test_instance_of_and_q
   :linenos:

Polymorphic filtering (for fields in inherited classes)
-------------------------------------------------------

.. literalinclude:: ../src/polymorphic/tests/examples/advanced/tests.py
   :caption: src/polymorphic/tests/examples/advanced/tests.py (field filtering)
   :language: python
   :pyobject: AdvancedExamplesTests.test_polymorphic_field_filtering
   :linenos:

ManyToManyField, ForeignKey, OneToOneField
------------------------------------------

.. literalinclude:: ../src/polymorphic/tests/examples/advanced/models.py
   :caption: src/polymorphic/tests/examples/advanced/models.py (many-to-many model)
   :language: python
   :pyobject: RelatingModel
   :linenos:

.. literalinclude:: ../src/polymorphic/tests/examples/advanced/tests.py
   :caption: src/polymorphic/tests/examples/advanced/tests.py (many-to-many polymorphic results)
   :language: python
   :pyobject: AdvancedExamplesTests.test_many_to_many_returns_real_instances
   :linenos:

Copying Polymorphic objects
---------------------------

.. literalinclude:: ../src/polymorphic/tests/examples/advanced/tests.py
   :caption: src/polymorphic/tests/examples/advanced/tests.py (copy + non_polymorphic behavior)
   :language: python
   :pyobject: AdvancedExamplesTests.test_copy_and_non_polymorphic
   :linenos:

Non-Polymorphic Queries
-----------------------

If you insert :meth:`~polymorphic.managers.PolymorphicQuerySet.non_polymorphic` anywhere into the
query chain, django-polymorphic returns base instances until you call
:meth:`~polymorphic.managers.PolymorphicQuerySet.get_real_instances`.

Restrictions & Caveats
----------------------

* Database performance caveats around concrete model inheritance still apply.
* ``values()``, ``values_list()``, and ``select_related()`` support limitations still apply.
* Enhanced filter definitions/Q-objects work in polymorphic queryset APIs.
