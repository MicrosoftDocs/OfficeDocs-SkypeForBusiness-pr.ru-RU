---
title: Обновление AAD подключения для включения более одного леса
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержит подробное описание действий по обновлению AAD подключиться к включению более одного леса в качестве части консолидации облако для групп и Скайп для бизнеса.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247713"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="0a9cf-103">Обновление AAD подключения для включения более одного леса</span><span class="sxs-lookup"><span data-stu-id="0a9cf-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="0a9cf-104">Подключение Azure AD поддерживает [синхронизацию из нескольких лесов](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="0a9cf-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="0a9cf-105">Тем не менее он поддерживает только один экземпляр синхронизации Azure AD подключиться к AAD.</span><span class="sxs-lookup"><span data-stu-id="0a9cf-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="0a9cf-106">Таким образом, в тех случаях, уже установленной Azure AD в одном лесу, необходимо обновить существующий экземпляр AAD подключения для синхронизации из дополнительных леса.</span><span class="sxs-lookup"><span data-stu-id="0a9cf-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="0a9cf-107">Если все удостоверения, представленные только один раз в обоих лесах (то есть, не было выполнено все контакты с включенной поддержкой почты), а затем просто повторно запустить мастер AAD подключения, нажмите кнопку «Настройка параметров синхронизации» и подключите свои каталоги на \*\* \*\*введите имя дополнительного леса и учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0a9cf-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="0a9cf-108">![Подключение страницы каталоги](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="0a9cf-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="0a9cf-109">Тем не менее если пользователи могут существовать в более чем одного каталога и вы будете объединения данных (например, если существуют объекты контактов в соответствии с пользователями в другом лесу лес), необходимо будет удалить подключение Azure AD и повторно установить его.</span><span class="sxs-lookup"><span data-stu-id="0a9cf-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="0a9cf-110">Это условие правила соединения между лесами можно настроить только во время первой установки.</span><span class="sxs-lookup"><span data-stu-id="0a9cf-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="0a9cf-111">Для этого на следующей странице:</span><span class="sxs-lookup"><span data-stu-id="0a9cf-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="0a9cf-112">![Однозначно идентифицирующая страницы пользователей](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="0a9cf-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="0a9cf-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0a9cf-113">See also</span></span>

[<span data-ttu-id="0a9cf-114">Консолидация облако для групп и Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0a9cf-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)