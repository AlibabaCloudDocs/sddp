# 授权SDDP访问云资源

使用敏感数据保护（SDDP）服务前，您需要先完成允许SDDP访问云资源的授权。本文档介绍如何进行云资源授权。

您已购买SDDP实例。

您购买SDDP实例后，首次登录SDDP控制台时，概览页面会提示您执行云资源授权的流程。完成授权后，您的SDDP实例才能访问OSS、RDS、MaxCompute等云服务的资源，并对这些云资源进行敏感数据扫描和分析等操作。

## 操作步骤

1.  登录[敏感数据保护控制台](https://yundun.console.aliyun.com/?p=sddp#/overview)。

2.  在概览页面单击**立即授权**。

    当您单击立即授权后，阿里云将自动为您创建SDDP服务关联角色AliyunServiceRoleForSDDP。您可以在[RAM控制台](https://ram.console.aliyun.com/roles)的角色管理页面查看系统为您自动创建的服务关联角色。您也可以使用API、CLI调用ListRoles，在返回结果中查看SDDP服务的关联角色。更多信息，请参见[服务关联角色](/intl.zh-CN/角色管理/服务关联角色.md)。

    完成授权SDDP访问云资源操作后，您需要进行资产保护授权才能进行敏感数据扫描和分析等操作。具体操作，请参见[数据资产授权](/intl.zh-CN/用户指南/数据资产授权.md)。


## SDDP服务关联角色介绍

角色名称：AliyunServiceRoleForSDDP

角色权限策略：AliyunServiceRolePolicyForSDDP

## 删除服务关联角色

当您不再需要使用SDDP服务时，可以删除SDDP的服务关联角色。您可以登录[RAM控制台](https://ram.console.aliyun.com/roles)删除AliyunServiceRoleForSDDP角色，具体操作，请参见[服务关联角色](/intl.zh-CN/角色管理/服务关联角色.md)。

## 相关说明

首次使用SDDP需要进行的云资源授权，与SDDP提供的资产保护授权功能，是两个不同的操作。云资源授权是允许SDDP访问其他提供数据服务的云产品，资产保护授权功能是允许SDDP访问具体的云产品中存有数据的部分空间或项目。完成授权SDDP访问云资源操作后，您需要进行资产保护授权才能进行敏感数据扫描和分析等操作。具体操作，请参见[数据资产授权](/intl.zh-CN/用户指南/数据资产授权.md)。

