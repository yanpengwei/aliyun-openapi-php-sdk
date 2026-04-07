# Open API SDK for PHP developers

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](License.md)

## Abandoned Notice

We have released a new SDK that supports Composer and gradually stop maintenance this version. Welcome to the new SDK: [**Alibaba Cloud SDK for PHP**](https://github.com/aliyun/openapi-sdk-php)

## 已废弃声明

此版本 SDK 已经废弃，请使用支持 Composer 的新版 SDK: [**Alibaba Cloud SDK for PHP**](https://github.com/aliyun/openapi-sdk-php)

---

## Overview / 概述

This repository contains the Alibaba Cloud Open API SDK for PHP developers. It provides PHP client libraries for accessing various Alibaba Cloud services through their Open APIs.

本仓库包含阿里云开放 API 的 PHP SDK，为 PHP 开发者提供访问各种阿里云服务的客户端库。

## Features / 特性

- **Comprehensive Service Coverage**: Supports 100+ Alibaba Cloud products including ECS, RDS, OSS, SLB, VPC, and more.
  **全面的服务覆盖**: 支持 100+ 阿里云产品，包括 ECS、RDS、OSS、SLB、VPC 等。

- **Easy Integration**: Simple installation and integration into your PHP projects.
  **易于集成**: 简单的安装和集成到您的 PHP 项目中。

- **Official Support**: Maintained by Alibaba Cloud team.
  **官方支持**: 由阿里云团队维护。

## Installation / 安装

### Manual Installation / 手动安装

1. Download or clone this repository
   下载或克隆此仓库

2. Include the core SDK in your project:
   在您的项目中包含核心 SDK：

```php
include_once '/path/to/aliyun-php-sdk-core/Autoloader.php';
\Acs\Autoloader::getInstance()->autoload();
```

3. Initialize the client:
   初始化客户端：

```php
use Acs\Core\DefaultAcsClient;
use Acs\Core\Profile\DefaultProfile;

$profile = DefaultProfile::getProfile("cn-hangzhou", "your-access-key-id", "your-access-key-secret");
$client = new DefaultAcsClient($profile);
```

## Usage Example / 使用示例

### ECS Example / ECS 示例

```php
<?php
include_once '/path/to/aliyun-php-sdk-core/Autoloader.php';
\Acs\Autoloader::getInstance()->autoload();

use Acs\Core\Profile\DefaultProfile;
use Acs\Core\DefaultAcsClient;
use Acs\Request\Ecs\V20140526 as Ecs;

// Create client profile
$profile = DefaultProfile::getProfile("cn-hangzhou", "your-access-key-id", "your-access-key-secret");
$client = new DefaultAcsClient($profile);

// Create request
$request = new Ecs\DescribeInstancesRequest();
$request->setRegionId("cn-hangzhou");
$request->setPageSize(10);

// Send request
$response = $client->getAcsResponse($request);
print_r($response);
?>
```

## Supported Products / 支持的产品

This SDK includes support for 100+ Alibaba Cloud products. Here are some of the major ones:

本 SDK 支持 100+ 阿里云产品，以下是一些主要产品：

- **Compute**: ECS (Elastic Compute Service), ECI (Elastic Container Instance)
- **Database**: RDS (Relational Database Service), Redis, MongoDB, PolarDB
- **Network**: VPC (Virtual Private Cloud), SLB (Server Load Balancer), CDN
- **Storage**: OSS (Object Storage Service), NAS (Network Attached Storage)
- **Security**: Security Center, Web Application Firewall, DDoS Protection
- **Messaging**: SMS, Voice Service, Push Notification
- **Big Data**: MaxCompute, DataWorks, E-MapReduce
- **AI & ML**: Machine Learning Platform, Image Search, NLP
- **IoT**: IoT Platform, Link WAN
- **Management**: CloudMonitor, ActionTrail, Resource Orchestration Service

For a complete list, please refer to the individual product SDK folders in this repository.
完整列表请参考此仓库中的各个产品 SDK 文件夹。

## Directory Structure / 目录结构

```
aliyun-php-sdk/
├── aliyun-php-sdk-core/          # Core SDK library / 核心 SDK 库
├── aliyun-php-sdk-ecs/           # ECS service SDK / ECS 服务 SDK
├── aliyun-php-sdk-rds/           # RDS service SDK / RDS 服务 SDK
├── aliyun-php-sdk-oss/           # OSS service SDK / OSS 服务 SDK
├── ...                           # Other product SDKs / 其他产品 SDK
├── README.md                     # This file / 本文件
└── License.md                    # Apache License 2.0 / Apache 许可证 2.0
```

## Requirements / 系统要求

- PHP 5.3 or higher
- cURL extension enabled
- JSON extension enabled

## Authentication / 认证

The SDK supports the following authentication methods:

SDK 支持以下认证方式：

1. **AccessKey Pair**: Use your Alibaba Cloud AccessKey ID and AccessKey Secret
   **AccessKey 对**: 使用您的阿里云 AccessKey ID 和 AccessKey Secret

2. **STS Token**: Security Token Service for temporary credentials
   **STS Token**: 安全令牌服务，用于临时凭证

3. **RAM Role**: Resource Access Management roles
   **RAM 角色**: 资源访问管理角色

## Documentation / 文档

- [Alibaba Cloud Open API Documentation](https://www.alibabacloud.com/help/doc-detail)
- [API Reference](https://next.api.aliyun.com/)
- [New SDK Repository](https://github.com/aliyun/openapi-sdk-php)

## Support / 支持

If you encounter any issues or have questions:

如果您遇到任何问题或有疑问：

1. Check the [FAQ](https://help.aliyun.com/product/29778.html)
2. Open an issue on GitHub
3. Contact Alibaba Cloud Support

## Contributing / 贡献

**Note**: This version of the SDK is deprecated. We recommend contributing to the new SDK at [Alibaba Cloud SDK for PHP](https://github.com/aliyun/openapi-sdk-php).

**注意**: 此版本的 SDK 已废弃。我们建议您向新的 SDK 贡献代码：[Alibaba Cloud SDK for PHP](https://github.com/aliyun/openapi-sdk-php)。

## License / 许可证

Copyright 1999-2019 Alibaba Group Holding Ltd.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

详见 [License.md](License.md) 文件。
