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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205080"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="bbc9d-103">Какие существуют ограничения специального символа в политиках групп?</span><span class="sxs-lookup"><span data-stu-id="bbc9d-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="bbc9d-104">**Хотя специальных символов можно использовать для создания политики групп с помощью PowerShell, который будет ограничен при управлении эти политики.  Таким образом мы настоятельно рекомендуем имена политики не включать специальные символы.**</span><span class="sxs-lookup"><span data-stu-id="bbc9d-104">**Although special characters can be used for creating Teams policies with PowerShell, you will be limited in managing these policies .  As such, we strongly recommend policy names do not include special characters.**</span></span>

<span data-ttu-id="bbc9d-105">Имена политики, созданные с помощью PowerShell для собраний и чата в группах может иметь специальные символы, таких как @, #, $.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-105">Policy names that you create using PowerShell for meetings and chat in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="bbc9d-106">Тем не менее если которым требуется для изменения политики в Microsoft групп и Скайп по центру администрирования бизнеса, не будут иметь возможность.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-106">However, if you are wanting to edit the policy in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="bbc9d-107">Необходимо использовать Windows PowerShell и командлет правильный политики для внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="bbc9d-108">Если у вас есть объект политики со специальными знаками и удалить специальных символов, чтобы лучше управлять политики в Microsoft групп и Скайп по центру администрирования бизнес, вам потребуется использовать ниже процедуры.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-108">If you have a policy object with special characters and you want to remove the special characters in order to better manage the policy in the Microsoft Teams and Skype for Business admin center, you will need to use the below procedure.</span></span> 

<span data-ttu-id="bbc9d-109">Примечание: В процедуре определена здесь используется пример политики системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-109">Note: The procedure articulated here uses the example of a Messaging policy.</span></span>  <span data-ttu-id="bbc9d-110">Тот же самый процесс используется для другого типа политики (собрания для примера) subsituting соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-110">The same process would be used for another policy type (Meetings for example) by subsituting the relevant cmdlets.</span></span> 

<span data-ttu-id="bbc9d-111">1.) вызов Get-CSMessagingPolicy-identity < old_policy_name > и запись данных выходные данные политики.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-111">1.) Call Get-CSMessagingPolicy -identity <old_policy_name> and capture the output of the policy.</span></span>
<span data-ttu-id="bbc9d-112">2.) вызова Set-CSMessagingPolicy-identity < new_policy_name >, чтобы создать новую политику с такой же конфигурацией, что исходной политики, но без специальные символы в имени.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-112">2.) Call Set-CSMessagingPolicy -identity <new_policy_name> to create a new policy with the same configuration as the original policy but without any special characters in the name.</span></span>
<span data-ttu-id="bbc9d-113">3.) вызова Delete-CSMessagingPolicy-identity < old_policy_name > Удалить политику.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-113">3.) Call Delete-CSMessagingPolicy -identity <old_policy_name> to delete the policy.</span></span>  <span data-ttu-id="bbc9d-114">Если эта команда выполнена успешно, вы все готово и можно приступить к назначение пользователей в новую политику, используя либо PowerShell, или группами Майкрософт и Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-114">If this command succeeds, you're done and can begin to assign users to the new policy using either PowerShell or the Microsoft Teams and Skype for Business admin center.</span></span>
<span data-ttu-id="bbc9d-115">4.) Если выше команда завершится неудачно, он является, поскольку старая политика назначена пользователю.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-115">4.) If the above command does not succeed, it is because the old policy has been assigned to a user.</span></span>  <span data-ttu-id="bbc9d-116">Запуск отменить командлет, чтобы отменить политику от пользователя, назначение новой политики, а затем снова запустите dwlete.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-116">Run unassign cmdlet to unassign the policy from user, assign new policy, then run dwlete again.</span></span>


