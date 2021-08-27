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
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы начать установку Skype для бизнеса Server, необходимо подготовить схему доменных служб Active Directory, лес и домены, на которые будут вмещать серверы и пользователи. Мастер Skype для бизнеса Server развертывания поможет вам с помощью действий, необходимых для подготовки Active Directory, начиная с схемы и затем в процессе подготовки леса. После подтверждения успешности репликации Active Directory необходимо подготовить каждый домен, в который будут приниматься пользователи или серверы.
ms.openlocfilehash: 082c80e4ee611a524f99919c744a2a1f49e2719d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578023"
---
# <a name="prepare-active-directory"></a>Подготовка Active Directory

Чтобы начать установку Skype для бизнеса Server, необходимо подготовить схему доменных служб Active Directory, лес и домены, на которые будут вмещать серверы и пользователи. Мастер Skype для бизнеса Server развертывания поможет вам с помощью действий, необходимых для подготовки Active Directory, начиная с схемы и затем в процессе подготовки леса. После подтверждения успешности репликации Active Directory необходимо подготовить каждый домен, в который будут приниматься пользователи или серверы.

> [!IMPORTANT]
> Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.

Подробные сведения о поддерживаемых топологиях Active Directory см. в разделе [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) в документации по технической поддержке. Подробные сведения о подготовке Active Directory см. в разделе [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) в документации по развертыванию.