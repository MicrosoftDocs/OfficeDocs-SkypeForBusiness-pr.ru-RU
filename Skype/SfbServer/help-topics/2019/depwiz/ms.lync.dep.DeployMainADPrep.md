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
description: Чтобы приступить к установке Skype для бизнес-сервера, необходимо подготовить схему доменных служб Active Directory, лес и домены, в которые будут вмещаться серверы и пользователи. Мастер развертывания Skype для бизнес-серверов поможет вам с помощью действий, необходимых для подготовки Active Directory, начиная с схемы и затем в процессе подготовки леса. После подтверждения успешности репликации Active Directory необходимо подготовить каждый домен, в который будут приниматься пользователи или серверы.
ms.openlocfilehash: fcc77ed8dab3a6e3e643c2022dc45623e855dfde
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097365"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="f96cb-105">Подготовка Active Directory</span><span class="sxs-lookup"><span data-stu-id="f96cb-105">Prepare Active Directory</span></span>

<span data-ttu-id="f96cb-106">Чтобы приступить к установке Skype для бизнес-сервера, необходимо подготовить схему доменных служб Active Directory, лес и домены, в которые будут вмещаться серверы и пользователи.</span><span class="sxs-lookup"><span data-stu-id="f96cb-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="f96cb-107">Мастер развертывания Skype для бизнес-серверов поможет вам с помощью действий, необходимых для подготовки Active Directory, начиная с схемы и затем в процессе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="f96cb-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="f96cb-108">После подтверждения успешности репликации Active Directory необходимо подготовить каждый домен, в который будут приниматься пользователи или серверы.</span><span class="sxs-lookup"><span data-stu-id="f96cb-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f96cb-p103">Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="f96cb-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="f96cb-112">Подробные сведения о поддерживаемых топологиях Active Directory см. в разделе [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) в документации по технической поддержке.</span><span class="sxs-lookup"><span data-stu-id="f96cb-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="f96cb-113">Подробные сведения о подготовке Active Directory см. в разделе [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f96cb-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>