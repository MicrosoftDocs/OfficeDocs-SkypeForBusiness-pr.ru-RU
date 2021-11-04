---
title: Подготовка Active Directory
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Чтобы начать установку Skype для бизнеса Server 2015 г., необходимо подготовить схему доменных служб Active Directory, лес и домены, в которые будут приниматься серверы и пользователи. Мастер Skype для бизнеса Server развертывания поможет вам с помощью действий, необходимых для подготовки Active Directory, начиная с схемы и затем в процессе подготовки леса. После подтверждения успешности репликации Active Directory необходимо подготовить каждый домен, в который будут приниматься пользователи или серверы.
ms.openlocfilehash: 3a83f41846a5795670b07ce17330dbd5b2bfde29
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770867"
---
# <a name="prepare-active-directory"></a>Подготовка Active Directory

Чтобы начать установку Skype для бизнеса Server 2015 г., необходимо подготовить схему доменных служб Active Directory, лес и домены, в которые будут приниматься серверы и пользователи. Мастер Skype для бизнеса Server развертывания поможет вам с помощью действий, необходимых для подготовки Active Directory, начиная с схемы и затем в процессе подготовки леса. После подтверждения успешности репликации Active Directory необходимо подготовить каждый домен, в который будут приниматься пользователи или серверы.

> [!IMPORTANT]
> Для успешной подготовки схемы вы должны войти как участник группы администраторов предприятия или группы администраторов схемы. Для подготовки леса вы должны войти как участник группы администраторов предприятия или как администратор в корне леса. Для подготовки домена вы должны войти как участник группы администраторов домена.

Подробные сведения о поддерживаемых топологиях Active Directory см. в разделе [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) в документации по технической поддержке. Подробные сведения о подготовке Active Directory см. в разделе [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) в документации по развертыванию.