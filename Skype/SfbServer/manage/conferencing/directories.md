---
title: Создание каталогов конференций в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Сводка: Узнайте, как для создания каталогов конференций в Скайп для Business Server.'
ms.openlocfilehash: 9e79ca7e1b2f896746db998cc53983c04c6724ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222753"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="35b93-103">Создание каталогов конференций в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="35b93-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="35b93-104">**Сводка:** Узнайте, как для создания каталогов конференций в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="35b93-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="35b93-105">Каталоги конференций Ведение сопоставления между собрания буквенно-цифровой идентификатор, который использует участника присоединиться к конференции, при использовании Скайп для бизнеса и конференции цифровой идентификатор, который использует телефонных конференций участника присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="35b93-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="35b93-106">Создание каталога конференции</span><span class="sxs-lookup"><span data-stu-id="35b93-106">Create a conference directory</span></span>

<span data-ttu-id="35b93-107">Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций.</span><span class="sxs-lookup"><span data-stu-id="35b93-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="35b93-p101">В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. Это правило позволит сохранить короткие идентификаторы конференций. Однако когда количество каталогов конференций (по пулам) превышает 9, длина идентификатора конференции будет увеличиваться для поддержки дополнительных конференций.</span><span class="sxs-lookup"><span data-stu-id="35b93-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="35b93-111">Формат идентификатора конференции:</span><span class="sxs-lookup"><span data-stu-id="35b93-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="35b93-p102">Для создания каталога конференций воспользуйтесь командлетом **New-CsConferenceDirectory**. Например, следующая команда создает каталог конференции с идентификатором 42, размещенный в пуле atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="35b93-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="35b93-114">Дополнительные сведения содержатся в разделе [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35b93-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

