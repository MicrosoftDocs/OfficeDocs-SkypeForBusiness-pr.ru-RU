---
title: Подготовка Active Directory
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
ms.openlocfilehash: 04e4baaaf5209c966fe9bfc350313f7e3cd25d22
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245183"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="8a7e1-105">Подготовка Active Directory</span><span class="sxs-lookup"><span data-stu-id="8a7e1-105">Prepare Active Directory</span></span>

<span data-ttu-id="8a7e1-106">Чтобы начать установку Скайп для Business Server, необходимо подготовить схемы доменных служб Active Directory, леса и домены, используемом для серверов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="8a7e1-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="8a7e1-107">Скайп для мастера развертывания сервера Business поможет выполнить действия, необходимые для подготовки Active Directory, Приступая к работе с использованием схемы, а затем в подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="8a7e1-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="8a7e1-108">После подтверждения, что репликация Active Directory будет успешно выполнена, затем Подготовка каждого домена, в котором будет размещаться пользователей или серверов.</span><span class="sxs-lookup"><span data-stu-id="8a7e1-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a7e1-p103">Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="8a7e1-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="8a7e1-112">Для получения дополнительных сведений о поддерживаемые топологии Active Directory содержатся в документации по поддержке [Поддержка Active Directory](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8a7e1-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="8a7e1-113">Для получения дополнительных сведений о подготовки Active Directory содержатся в документации по развертыванию [Overview of подготовка домена Active Directory Services](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8a7e1-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


