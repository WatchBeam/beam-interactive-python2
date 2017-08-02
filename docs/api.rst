API
===

This document describes the Python API to connect to Mixer's Interactive service. We assume you're already somewhat familiar with Interactive. If you're not, check our `reference guide <https://dev.mixer.com/reference/interactive/index.html>`_.

To connect to Interactive, you first need to have an Interactive project and some means of authentication. You'll want to `create an Interactive project <https://dev.mixer.com/reference/interactive/index.html#creating-an-interactive-project>`_ on Mixer and register an `OAuth client <https://dev.mixer.com/reference/oauth/index.html#registering>`_ while you're there. For most integrations, you can leave the OAuth "redirect URLs" empty, and you should not request a secret key.

You can now use the OAuthClient class with your OAuth client ID to get an access token.

OAuth
-----

.. autoclass:: beam_interactive2.OAuthClient
    :members:
    :undoc-members:

.. autoclass:: beam_interactive2.OAuthShortCode
    :members:
    :undoc-members:

    .. attribute:: code

        The short six-digit code to be displayed to the user. They should be prompted to enter it on `mixer.com/go <https://mixer.com/go>`_.

.. autoclass:: beam_interactive2.OAuthTokens
    :members:
    :undoc-members:

    .. attribute:: access

        The OAuth access token to use in :func:`~beam_interactive2.State.connect`.

    .. attribute:: refresh

        The OAuth refresh token that can be used to re-grant the access token.

    .. attribute:: expires_at

        The datetime at which the access token expires.

State
-----

.. autoclass:: beam_interactive2.State
    :members:
    :undoc-members:
    :show-inheritance:


Submodules
----------

beam_interactive2.connection module
-----------------------------------

.. automodule:: beam_interactive2.connection
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.discovery module
----------------------------------

.. automodule:: beam_interactive2.discovery
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.encoding module
---------------------------------

.. automodule:: beam_interactive2.encoding
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.errors module
-------------------------------

.. automodule:: beam_interactive2.errors
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.keycodes module
---------------------------------

.. automodule:: beam_interactive2.keycodes
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.log module
----------------------------

.. automodule:: beam_interactive2.log
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.scene module
------------------------------

.. automodule:: beam_interactive2.scene
    :members:
    :undoc-members:
    :show-inheritance:

beam_interactive2.state module
------------------------------

.. automodule:: beam_interactive2.state
    :members:
    :undoc-members:
    :show-inheritance:


Module contents
---------------

.. automodule:: beam_interactive2
    :members:
    :undoc-members:
    :show-inheritance:
