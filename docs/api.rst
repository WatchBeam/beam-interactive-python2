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

    .. attribute:: connection

        The underlying :class:`~beam_interactive2.Connection` to the Interactive service. You should not need to deal with this most of the time.

.. autoclass:: beam_interactive2.Discovery
    :members:
    :undoc-members:
    :show-inheritance:

Scenes
------

.. autoclass:: beam_interactive2.Scene
    :members:
    :undoc-members:
    :show-inheritance:

.. autoclass:: beam_interactive2.Control
    :members:
    :undoc-members:
    :show-inheritance:

.. autoclass:: beam_interactive2.Button
    :members:
    :undoc-members:
    :show-inheritance:

.. autoclass:: beam_interactive2.Joystick
    :members:
    :undoc-members:
    :show-inheritance:

Utilities
---------

.. data:: beam_interactive2.keycode

    Keycode is an instance of a class that helps translate keycodes from their textual representation to their corresponding numeric code, as represented on the protocol. For example::

        from beam_interactive2 import keycode

        print(keycode.up)     # => 38
        print(keycode.a)      # => 65
        getattr(keycode, '⌘') # => 91


.. autoclass:: beam_interactive2._util.ChangeTracker
    :members:
    :undoc-members:
    :show-inheritance:

.. autoclass:: beam_interactive2._util.Resource
    :members:
    :undoc-members:
    :show-inheritance:

Errors
------

.. autoclass:: beam_interactive2.DiscoveryError
    :show-inheritance:

.. autoclass:: beam_interactive2.NoServersAvailableError
    :show-inheritance:

.. autoclass:: beam_interactive2.ShortCodeError
    :show-inheritance:

.. autoclass:: beam_interactive2.UnknownShortCodeError
    :show-inheritance:

.. autoclass:: beam_interactive2.ShortCodeAccessDeniedError
    :show-inheritance:

.. autoclass:: beam_interactive2.ShortCodeTimeoutError
    :show-inheritance:

Low-Level Protocol
------------------

.. autoclass:: beam_interactive2.Connection
    :members:
    :undoc-members:
    :show-inheritance:

.. autoclass:: beam_interactive2.Call
    :members:
    :undoc-members:
    :show-inheritance:


.. automodule:: beam_interactive2.encoding
    :members:
    :undoc-members:
    :show-inheritance:
