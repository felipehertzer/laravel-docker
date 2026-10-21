# laravel-docker

🐳 Generic docker image for Laravel Applications

[![Docker Badge](https://img.shields.io/docker/pulls/lorisleiva/laravel-docker)](https://hub.docker.com/r/lorisleiva/laravel-docker/)

| Tags   | PHP version | Architecture | Features                                                                                                        |
|--------|-------------|-------------|-----------------------------------------------------------------------------------------------------------------|
| 8.4    | 8.4         | amd64/arm64 | ✅ Everything.                                                                                                   |
| 8.5    | 8.5         | amd64/arm64 | ✅ Everything.                                                                                                   |
| 8.6    | 8.6 (RC)    | amd64/arm64 | ⚠️ No `imagick`, `redis` or `xdebug`: no PHP 8.6 compatible release yet. RC until 19 Nov 2026.   |
| stable | **8.4**     | amd64/arm64 | 🔗 Aliases the latest stable version of PHP that supports all features of this docker image.                    |
| latest | **8.5**     | amd64/arm64 | 🔗 Aliases the latest stable version of PHP available (even if that version does not support all features yet). |

#### Use within your GitLab's pipelines.

- [Run test suite and check codestyle](http://lorisleiva.com/using-gitlabs-pipeline-with-laravel/)
- [Build, test and deploy your Laravel application](http://lorisleiva.com/laravel-deployment-using-gitlab-pipelines/)
