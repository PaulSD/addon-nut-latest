# Home Assistant Community Add-on: Network UPS Tools (Latest version)

A ["Network UPS Tools"][addon-nut] add-on based on Debian Stable is already available from the
"Home Assistant Community Add-ons" repository.  However, the version of NUT in Debian Stable is
typically significantly outdated.

For users who need (or want to test with) a newer version of NUT,
this add-on is based on the "Network UPS Tools" add-on but it provides the version of NUT in
Debian Unstable (Sid).

For more background on NUT, see the ["Network UPS Tools" add-on docs][addon-nut-docs].

## Installation

1. Add this add-on to Home Assistant, either using this button:

   [![Open this add-on in your Home Assistant instance.][addon-inst-badge]][addon-inst]

   Or by going to "Settings" -> "Add-ons" -> "Add-on store" (bottom right)
   -> Menu button (three dots, top right) -> Repositories
   -> Add https://github.com/PaulSD/addons-nut -> Close -> Search for "nut"
   -> "Network UPS Tools (Latest version)" -> "Install".

1. Copy the add-on config from the "Network UPS Tools" add-on to the
   "Network UPS Tools (Latest version)" add-on: "Settings" -> "Add-ons" -> "Network UPS Tools"
   -> "Configuration" -> Menu button (three dots, top right) -> "Edit in YAML" -> Ctrl+a CTRL+c in
   the text box -> Back button (arrow, top left) -> "Network UPS Tools (Latest version)"
   -> "Configuration" -> Menu button (three dots, top right) -> "Edit in YAML" -> Ctrl+v in the text
   box -> Save.

   If you have not previously configured the "Network UPS Tools" add-on, then configure at least the
   `users` and `devices` options as described in the
   ["Network UPS Tools" add-on docs][addon-nut-docs-conf].
1. Stop and disable the "Network UPS Tools" add-on ("Settings" -> "Add-ons" -> "Network UPS Tools"
   -> "Info" tab -> "Stop" -> Disable "Start on boot").  (Only one of the "Network UPS Tools" or
   "Network UPS Tools (Latest version)" add-ons can be running at a time.)
1. Start the "Network UPS Tools (Latest version)" add-on ("Settings" -> "Add-ons"
   -> "Network UPS Tools (Latest version)" -> "Info" tab -> "Start" -> Enable "Start on boot").
1. Check the "Logs" tab of the "Network UPS Tools (Latest version)" add-on for any issues.
1. Note the `Hostname` listed on the "Info" tab of the "Network UPS Tools (Latest version)" add-on.
1. Update the Hostname used by the NUT Integration: "Settings" -> "Devices & services"
   -> "Integrations" tab -> "Network UPS Tools (NUT)"
   -> Menu button (three dots) to the right of the host:port (not to the right of the UPS)
   -> "Reconfigure" -> Update the "Host" field to the add-on Hostname identified above -> Submit.

   If you have not previously configured the NUT Integration, then configure it according to the
   [docs][nut-ha-docs], using the add-on Hostname identified above, Port `3493`, and the
   Username/Password configured in the add-on.

## Configuration

This add-on provides the same configuration options as the "Network UPS Tools" add-on.  See that
add-on's [config documentation][addon-nut-docs-conf] for details.

## Support

For issues with the NUT software that are not related to the Home Assistant Add-on
configuration/execution environment (eg. driver/compatibility issues or crashes), see the
[NUT support instructions][nut-help].

Since this add-on is based on the ["Network UPS Tools"][addon-nut] add-on, if you find any issues
with this add-on's configuration/execution environment then please first check whether the issue is
also present in the "Network UPS Tools" add-on, and if so then report the issue as described in that
add-on's [documentation][addon-nut-docs-help].

If you find an issue that is specific to this add-on's configuration/execution environment (and is
not inherited from the "Network UPS Tools" add-on) then you can open a [GitHub issue][github-issue].

## Authors & contributors

This repository/add-on was initially set up by [Paul Donohue][paulsd].

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2025 Authors/Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[addon-inst-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon-inst]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=40e42f29_nut-latest&repository_url=https%3A%2F%2Fgithub.com%2FPaulSD%2Faddons-nut
[addon-nut]: https://github.com/hassio-addons/addon-nut
[addon-nut-docs]: https://github.com/hassio-addons/addon-nut/blob/main/nut/DOCS.md
[addon-nut-docs-conf]: https://github.com/hassio-addons/addon-nut/blob/main/nut/DOCS.md#configuration
[addon-nut-docs-help]: https://github.com/hassio-addons/addon-nut/blob/main/nut/DOCS.md#support
[nut-ha-docs]: https://www.home-assistant.io/integrations/nut/
[nut-help]: https://networkupstools.org/support.html
[github-issue]: https://github.com/PaulSD/addons-nut/issues
[paulsd]: https://github.com/PaulSD
[contributors]: https://github.com/PaulSD/addons-nut/graphs/contributors
