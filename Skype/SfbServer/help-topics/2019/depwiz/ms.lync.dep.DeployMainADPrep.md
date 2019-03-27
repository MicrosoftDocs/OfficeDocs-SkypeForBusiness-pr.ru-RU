---
title: Подготовка Active Directory
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы начать установку Скайп для Business Server, необходимо подготовить схемы доменных служб Active Directory, леса и домены, используемом для серверов и пользователей. Скайп для мастера развертывания сервера Business поможет выполнить действия, необходимые для подготовки Active Directory, Приступая к работе с использованием схемы, а затем в подготовки леса. После подтверждения, что репликация Active Directory будет успешно выполнена, затем Подготовка каждого домена, в котором будет размещаться пользователей или серверов.
ms.openlocfilehash: be4d0b6dbd5ee7ff69bdf0a1e354ca5529fdef0b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897152"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="7ae98-105">Подготовка Active Directory</span><span class="sxs-lookup"><span data-stu-id="7ae98-105">Prepare Active Directory</span></span>

<span data-ttu-id="7ae98-106">Чтобы начать установку Скайп для Business Server, необходимо подготовить схемы доменных служб Active Directory, леса и домены, используемом для серверов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ae98-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="7ae98-107">Скайп для мастера развертывания сервера Business поможет выполнить действия, необходимые для подготовки Active Directory, Приступая к работе с использованием схемы, а затем в подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="7ae98-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="7ae98-108">После подтверждения, что репликация Active Directory будет успешно выполнена, затем Подготовка каждого домена, в котором будет размещаться пользователей или серверов.</span><span class="sxs-lookup"><span data-stu-id="7ae98-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ae98-p103">Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="7ae98-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="7ae98-p104">Подробные сведения о поддерживаемых топологиях Active Directory см. в разделе [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) в документации по технической поддержке. Подробные сведения о подготовке Active Directory см. в разделе [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7ae98-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


