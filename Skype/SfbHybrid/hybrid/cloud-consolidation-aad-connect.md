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
description: В этом приложении содержатся подробные инструкции по обновлению AAD Connect для включения нескольких лесов в состав облачной консолидации для Teams и Skype для бизнеса.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049101"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="94968-103">Обновление AAD Connect для включения нескольких лесов</span><span class="sxs-lookup"><span data-stu-id="94968-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="94968-104">Azure AD Connect поддерживает [синхронизацию из нескольких лесов](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="94968-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="94968-105">Однако он поддерживает только один экземпляр Azure AD Connect Sync to AAD.</span><span class="sxs-lookup"><span data-stu-id="94968-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="94968-106">Таким образом, если служба Azure AD уже установлена в одном лесу, существующий экземпляр AAD Connect необходимо обновить для синхронизации с дополнительным лесом.</span><span class="sxs-lookup"><span data-stu-id="94968-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="94968-107">Если все удостоверения представлены только один раз в обоих лесах (то есть контакты с включенной поддержкой почты не были настроены), можно просто повторно запустить мастер подключения AAD, выбрать пункт "Настройка параметров синхронизации", а затем на странице **подключить каталоги** введите имя дополнительного леса и учетных записей.</span><span class="sxs-lookup"><span data-stu-id="94968-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="94968-108">![Страница подключения каталогов](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="94968-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="94968-109">Тем не менее, если пользователи могут находиться в нескольких каталогах и вы будете объединять данные (например, если объекты Contact существуют в лесу, соответствующем пользователям в другом лесу), необходимо удалить Azure AD Connect и повторно установить ее.</span><span class="sxs-lookup"><span data-stu-id="94968-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="94968-110">Это связано с тем, что условие правил подключения между лесами можно настроить только при первой установке.</span><span class="sxs-lookup"><span data-stu-id="94968-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="94968-111">Это делается на следующей странице:</span><span class="sxs-lookup"><span data-stu-id="94968-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="94968-112">![Страница уникальной идентификации пользователей](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="94968-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="94968-113">См. также</span><span class="sxs-lookup"><span data-stu-id="94968-113">See also</span></span>

[<span data-ttu-id="94968-114">Объединение в облако для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="94968-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)