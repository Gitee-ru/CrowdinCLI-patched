This repository contains source code of Gitee Enterprise plugin for module PIPE.
To create tasks that download a localization dump from the Crowdin localization management tool and commit changes to the GIT repository of module CODE, you can use the plugin.

## Plugin Installation
1. Navigate to the Plugin market of the Gitee Enterprise Instance
2. Create new plugin and fill parameters:
- **Icon** - upload SVG icon from the version folder
- **Plugin Name** - 'Crowdin Downloader'
- **Plugin Identity** - 'CrowdinDownloader'
- **Classification** - 'Tool'
3. Add new version and fill content from the file 'release.yaml' from the version folder
4. Install version
5. Release version

For more details refer [Gitee PIPE plugin market operation guide](https://docs.gitee.ru/docs/user-guide/gitee-pipe/pipe-manager/)


## Plugin parameters
Description of User's parameters that need to fill during task creation.
Set of parameters can be different in the different versions of Plugin.

### V1.0

- **'Gitee Git user SSH private key'**: Gitee executes tasks in a dedicated container. The system propagates a private key to the container runtime environment to ensure the successful completion of git push events. The public key must be loaded onto the personal account of a valid user in the Gitee Enterprise tenant.
- **'Gitee Git Commiter email'**: The email address associated with a valid user's Git account on the Gitee tenant.

## Create Pipeline in Gitee Pipe
The exact pipeline configuration will depend on the workflow adopted for the localization project. The following is an example pipeline configuration for such a scenario:
- The master branch stores the version of the localization onboarder that matches the latest product version.
- The localization is downloaded to Gitee on a daily basis and stored in the development branch.
- Localization changes to all files of the project are tracked in a single commit.

Pipeline creation and exection description in [documentation](https://gitee-docs-dev.website.yandexcloud.net/docs/user-guide/gitee-pipe/pipe-quickstart/)

- As pipeline source need to select target repository that manages localiazation source and translation results
- Select default branch that will be used as target branch: develop
- Specify crowdin project and authentication information as pipeline [global parameters](https://docs.gitee.ru/docs/user-guide/gitee-pipe/pipeline/pipeline-create/#%D0%B3%D0%BB%D0%BE%D0%B1%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%BF%D0%B0%D0%B9%D0%BF%D0%BB%D0%B0%D0%B9%D0%BD%D0%B0)
- Specify daily pipeline run scedule in the [common pipelene parameters](https://docs.gitee.ru/docs/user-guide/gitee-pipe/pipeline/pipeline-create/#%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B--%D0%BF%D0%B0%D0%B9%D0%BF%D0%BB%D0%B0%D0%B9%D0%BD%D0%B0)






