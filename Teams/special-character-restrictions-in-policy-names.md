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
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="3ca7f-103">Какие существуют ограничения специального символа в политиках групп?</span><span class="sxs-lookup"><span data-stu-id="3ca7f-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="3ca7f-104">**Несмотря на то, что можно использовать специальные символы в именах политики, которую вы создали в группах, мы настоятельно рекомендуем вам не.**</span><span class="sxs-lookup"><span data-stu-id="3ca7f-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="3ca7f-105">Имена политики, создайте для собрания, беседы и prescense, а другие действия в группах могут иметь специальные знаки, такие как @, #, $.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="3ca7f-106">Тем не менее если которым требуется внесение изменений в имя в группами Майкрософт и Скайп по центру администрирования бизнеса, не будут иметь возможность.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="3ca7f-107">Необходимо использовать Windows PowerShell и командлет правильный политики для внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="3ca7f-108">Например при наличии политика собрания со специальными знаками и вы хотите изменить имя или удалите из имени специальные символы, необходимо с помощью командлета Set-CsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="3ca7f-109">Ниже приведен список командлетов политики, которые необходимо сделать это:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="3ca7f-110">SET-CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca7f-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="3ca7f-111">SET-CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca7f-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="3ca7f-112">SET-\*</span><span class="sxs-lookup"><span data-stu-id="3ca7f-112">Set-\*</span></span>


