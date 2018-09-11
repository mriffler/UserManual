########
Playbook
########

.. _classificationMap:
.. figure:: images/ClassificationMap.png
   :name: classificationMapName
   :scale: 80%
   :alt: table of scene classification
   :align: center

   Classification Map

   The legend consists of all elements after the caption.  In this
   case, the legend consists of this paragraph and the following
   table:

   +-----------------------+-----------------------+
   | Symbol                | Meaning               |
   +=======================+=======================+
   | A                     | Campground            |
   +-----------------------+-----------------------+
   | B                     | Lake                  |
   +-----------------------+-----------------------+
   | C                     | Mountain              |
   +-----------------------+-----------------------+




This is a simple reference using a **label** to :ref:`classificationMap`

This is a simple reference using a **name** to :ref:`classificationMapName`

This is a numbered reference using :numref:`classificationMap`
Page must be included/referenced in index (toc) in order items being numbered.

This is a enhanced numbered reference :numref:`nicely numbered figure (Fig. {number}) with the caption: {name} <classificationMap>`

See also: :numref:`Table {number} {name} <bandTable>`



Equations
*********

see also `Math <http://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html?highlight=equation#math>`_
and `Options <http://www.sphinx-doc.org/en/master/usage/configuration.html#options-for-math>`_
and `Short Math Guide for LATEX <http://ftp.fau.de/ctan/info/short-math-guide/short-math-guide.pdf>`_

Since Pythagoras, we know that :math:`a^2 + b^2 = c^2`.


:math:`(a + b)^2 = a^2 + 2ab + b^2`

:math:`(a - b)^2 = a^2 - 2ab + b^2`


.. math::
   :nowrap:

   \begin{eqnarray}
      y    & = & ax^2 + bx + c \\
      f(x) & = & x^2 + 2xy + y^2
   \end{eqnarray}

.. math::

   Î±_t(i) = P(O_1, O_2, â€¦ O_t, q_t = S_i Î») =\Sigma

.. math::

   A_\infty + \pi A_0
   \sim \mathbf{A}_{\boldsymbol{\infty}} \boldsymbol{+}
   \boldsymbol{\pi} \mathbf{A}_{\boldsymbol{0}}
   \sim\pmb{A}_{\pmb{\infty}} \pmb{+}\pmb{\pi} \pmb{A}_{\pmb{0}}

.. math::

   \Gamma, \Delta, \Lambda, \Phi, \Pi, \Psi, \Sigma, \Theta, \Upsilon, \Xi, \Omega

.. math::

   NDVI=\frac{\rho_{B8} - \rho_{B4}}{\rho_{B8} + \rho_{B4}}


.. _bandTable:

.. table:: Sentinel bands

   +------------------------+-----------------+---------------+
   | Band name              |  Central        | Spatial       |
   |                        |  Wavelength (nm)| Resolution (m)|
   +========================+=================+===============+
   | B01                    | 443             | 60            |
   +------------------------+-----------------+---------------+
   | B02                    | 490             | 10            |
   +------------------------+-----------------+---------------+
   | B03                    | 560             | 10            |
   +------------------------+-----------------+---------------+

