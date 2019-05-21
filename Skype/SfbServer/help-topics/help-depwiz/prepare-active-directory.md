---
title: Подготовка Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Чтобы начать установку Skype для бизнеса Server 2015, необходимо подготовить схему доменных служб Active Directory, леса и домены, в которых будут размещаться серверы и пользователи. Мастер развертывания Skype для бизнеса Server поможет вам выполнить необходимые действия для подготовки Active Directory, начиная с схемы и затем до подготовки леса. После того как вы убедитесь в том, что репликация Active Directory выполнена успешно, необходимо подготовить каждый домен, в котором будут размещаться пользователи или серверы.
ms.openlocfilehash: a7b908bb1c6194e1b6d9b12a90d250d09815ea5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283755"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="ec81e-105">Подготовка Active Directory</span><span class="sxs-lookup"><span data-stu-id="ec81e-105">Prepare Active Directory</span></span>

<span data-ttu-id="ec81e-106">Чтобы начать установку Skype для бизнеса Server 2015, необходимо подготовить схему доменных служб Active Directory, леса и домены, в которых будут размещаться серверы и пользователи.</span><span class="sxs-lookup"><span data-stu-id="ec81e-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="ec81e-107">Мастер развертывания Skype для бизнеса Server поможет вам выполнить необходимые действия для подготовки Active Directory, начиная с схемы и затем до подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="ec81e-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="ec81e-108">После того как вы убедитесь в том, что репликация Active Directory выполнена успешно, необходимо подготовить каждый домен, в котором будут размещаться пользователи или серверы.</span><span class="sxs-lookup"><span data-stu-id="ec81e-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec81e-p103">Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="ec81e-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="ec81e-p104">Подробные сведения о поддерживаемых топологиях Active Directory см. в разделе [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) в документации по технической поддержке. Подробные сведения о подготовке Active Directory см. в разделе [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ec81e-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


