# 非公开版本

本文约定非公开版本`0.Y.Z`的使用方式。

昨天我在一个内部教学群摘取了Dart库对v0.x版本的约定，他们的定义是0.x.y+z，以类比x.y.z。Dart对依赖版本有一套明确的处理规范，所以需要公开发布的Dart和Flutter库的0.x版本遵循这个约定。

我们的情况略不一样。我们的大部分版本规划都是以产品特性为单位规划的，为了方便统一协调内部各个项目的进度。

课程平台目前采取中版本统一、小版本各个仓库独立的策略。比如，0.1版本约定为提供课程资源访问，Flutter、Django、API文档、PRD文档分别有自己的小版本。这些小版本的更新往往是不兼容的，我会在release note注明这个版本对上一个版本不兼容。

如果采取上述Dart库的策略，我们的版本管理将会变得复杂。我们经常会在一个特性的增加过程中反复改动字段等细节，也会频繁地重新设计和重构。也就是说，我们目前的情况是只要发布版本，几乎就会有不兼容更新。所以上述Dart库的规范对我们来说没有太大意义。

因此我们选择放弃Dart库推荐的理解，而采取我们的定义。中版本号定义特性，小版本号约定API。我们放弃Dart库和Python库的版本兼容，采取0.x版本必须被固定版本号使用的策略。

考虑到我们目前大部分项目都是0.x，还不存在1.x需要依赖0.x这种意外情况，因此暂不考虑。对于这类问题的解决办法，我们主要考虑优先稳定底层依赖API并发布1.0，然后再考虑上层库。因此，各个库的1.0版本的约定对于我们来说十分重要，关系到项目和项目之间的协作。