# Choosing Boilerplate

<!-- MarkdownTOC -->

- [Criteria](#criteria)
- [Options](#options)

<!-- /MarkdownTOC -->

<a name="criteria"></a>
# Criteria

 - Webpack
 - Smart router
 - ES6 transpilation
 - Up to date

<a name="options"></a>
# Options

 - [react-starter][react-starter]
 - [react-webpack-boilerplate][react-webpack-boilerplate]

|                                   | [react-starter][react-starter]                                  | [react-webpack-boilerplate][react-webpack-boilerplate]                  |
| ---                               | ---                                                             | ---                                                                     |
|                                   | **CHOICE**                                                      |                                                                         |
| webpack version in `package.json` | ^1.8.1                                                          | 1.10.1                                                                  |
| [Vagrant][vagrant]                | required                                                        | n/a                                                                     |
| last update                       | 2015-09-01                                                      | 2015-07-28                                                              |
| client files                      | ![./choosing-boilerplate/webpack-react-starter.png](screenshot) | ![./choosing-boilerplate/srn-react-webpack-boilerplate.png](screenshot) |
| router                            | `"react-router": "^0.13.2"``                                    | ?                                                                       |
| server                            | `"webpack-dev-server": "^1.4.7"` and  `"express": "^4.7.2"`     | `"webpack-dev-server": "1.10.1"` and `"express": "4.13.1"`              |
| react                             | `"react": "^0.13.1"`                                            | `"react": "0.13.3"`                                                     |
| to run                            | `npm run dev-server`, `npm run start-dev`                       | `npm start`                                                             |

*[Vagrant][vagrant]: Create and configure lightweight, reproducible, and portable development environments.

[react-starter]: https://github.com/webpack/react-starter
[react-webpack-boilerplate]: https://github.com/srn/react-webpack-boilerplate
[vagrant]: https://www.vagrantup.com/