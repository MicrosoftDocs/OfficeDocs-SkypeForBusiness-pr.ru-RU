---
title: Подготовка Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы начать установку Skype для бизнеса Server, необходимо подготовить схему доменных служб Active Directory, лес и домены, в которые будут вмещаться серверы и пользователи. Мастер развертывания Skype для бизнеса Server поможет вам подготовить Active Directory, начиная со схемы, а затем до подготовки леса. После подтверждения успешности репликации Active Directory необходимо подготовить все домены, в которых будут работать пользователи или серверы.
ms.openlocfilehash: 4e2951643ddc0f569df6802b6ff5fdd8d2c12a82
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825055"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="89619-105">Подготовка Active Directory</span><span class="sxs-lookup"><span data-stu-id="89619-105">Prepare Active Directory</span></span>

<span data-ttu-id="89619-106">Чтобы начать установку Skype для бизнеса Server, необходимо подготовить схему доменных служб Active Directory, лес и домены, в которые будут вмещаться серверы и пользователи.</span><span class="sxs-lookup"><span data-stu-id="89619-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="89619-107">Мастер развертывания Skype для бизнеса Server поможет вам подготовить Active Directory, начиная со схемы, а затем до подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="89619-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="89619-108">После подтверждения успешности репликации Active Directory необходимо подготовить все домены, в которых будут работать пользователи или серверы.</span><span class="sxs-lookup"><span data-stu-id="89619-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89619-p103">Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="89619-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="89619-112">Подробные сведения о поддерживаемых топологиях Active Directory см. в разделе [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) в документации по технической поддержке.</span><span class="sxs-lookup"><span data-stu-id="89619-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="89619-113">Подробные сведения о подготовке Active Directory см. в разделе [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="89619-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


