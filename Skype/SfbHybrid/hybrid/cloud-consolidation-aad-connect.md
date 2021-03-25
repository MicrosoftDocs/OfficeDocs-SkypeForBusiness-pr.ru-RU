---
title: Обновление AAD Connect для включения нескольких лесов
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержатся подробные действия по обновлению AAD Connect, чтобы включить несколько лесов в рамках консолидации облаков для Teams и Skype для бизнеса.
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120378"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="2a262-103">Обновление AAD Connect для включения нескольких лесов</span><span class="sxs-lookup"><span data-stu-id="2a262-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="2a262-104">Azure AD Connect поддерживает [синхронизацию из нескольких лесов.](/azure/active-directory/connect/active-directory-aadconnect-topologies)</span><span class="sxs-lookup"><span data-stu-id="2a262-104">Azure AD Connect supports [syncing from multiple forests](/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="2a262-105">Однако он поддерживает только один экземпляр синхронизации Azure AD Connect с AAD.</span><span class="sxs-lookup"><span data-stu-id="2a262-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="2a262-106">Поэтому в случаях, когда Azure AD уже установлена в одном лесу, существующий экземпляр AAD Connect должен быть обновлен для синхронизации из дополнительного леса.</span><span class="sxs-lookup"><span data-stu-id="2a262-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="2a262-107">Если все удостоверения представлены только один раз в обоих лесах (то есть контакты с поддержкой почты не установлены), можно просто повторно запустить мастер AAD Connect, выбрать параметры синхронизации, а затем на странице **Connect Your Directories** введите имя дополнительного леса и creds.</span><span class="sxs-lookup"><span data-stu-id="2a262-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="2a262-108">![Страница Подключение каталогов](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="2a262-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="2a262-109">Однако, если пользователи могут существовать в более чем одном каталоге, и вы будете совмещать данные (например, если контактные объекты существуют в лесу, соответствующем пользователям в другом лесу), вам потребуется удалить Azure AD Connect и повторно установить его.</span><span class="sxs-lookup"><span data-stu-id="2a262-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="2a262-110">Это обусловлено тем, что условие правил межлесного присоединяться может быть настроено только во время первой установки.</span><span class="sxs-lookup"><span data-stu-id="2a262-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="2a262-111">Это делается на следующей странице:</span><span class="sxs-lookup"><span data-stu-id="2a262-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="2a262-112">![Страница Uniquely identifying your users](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="2a262-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="2a262-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2a262-113">See also</span></span>

[<span data-ttu-id="2a262-114">Консолидация облаков для команд и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2a262-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)