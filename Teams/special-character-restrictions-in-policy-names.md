---
title: Какие существуют ограничения специального символа в политиках групп?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: В разделе проблемы в имена политик и что можно сделать для fix it для есть со специальными знаками.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192166"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Какие существуют ограничения специального символа в политиках групп?

**Несмотря на то, что можно использовать специальные символы в именах политики, которую вы создали в группах, мы настоятельно рекомендуем вам не.**

Имена политики, создайте для собрания, беседы и prescense, а другие действия в группах могут иметь специальные знаки, такие как @, #, $. Тем не менее если которым требуется внесение изменений в имя в группами Майкрософт и Скайп по центру администрирования бизнеса, не будут иметь возможность. Необходимо использовать Windows PowerShell и командлет правильный политики для внесения изменений.

Например при наличии политика собрания со специальными знаками и вы хотите изменить имя или удалите из имени специальные символы, необходимо с помощью командлета Set-CsMeetingPolicy. 

Ниже приведен список командлетов политики, которые необходимо сделать это:
1. SET-CsMeetingPolicy
2. SET-CsAppPolicy
3. SET-*


