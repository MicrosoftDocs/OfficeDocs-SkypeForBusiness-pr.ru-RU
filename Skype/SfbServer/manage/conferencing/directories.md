---
title: Создание каталогов конференций в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: Сводка. Сведения о создании каталогов конференций в Skype для бизнеса Server.
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119478"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="04324-103">Создание каталогов конференций в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="04324-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="04324-104">**Сводка:** Узнайте, как создать каталоги конференций в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="04324-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="04324-105">Каталоги конференций поддерживают сопоставление между альфа-номерным ИД собрания, который участник использует, чтобы присоединиться к конференции при использовании Skype для бизнеса, и номерным ИД конференции, который используется участником конференц-связи для звонков.</span><span class="sxs-lookup"><span data-stu-id="04324-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="04324-106">Создание каталога конференций</span><span class="sxs-lookup"><span data-stu-id="04324-106">Create a conference directory</span></span>

<span data-ttu-id="04324-107">Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций.</span><span class="sxs-lookup"><span data-stu-id="04324-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="04324-108">В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="04324-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="04324-109">С помощью этого руководства, как правило, можно хранить небольшие ID конференции.</span><span class="sxs-lookup"><span data-stu-id="04324-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="04324-110">Однако, как только количество каталогов конференций (в пулах) превысит 9, длина ID конференции будет увеличиваться для поддержки дополнительных конференций.</span><span class="sxs-lookup"><span data-stu-id="04324-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="04324-111">Формат ID конференции:</span><span class="sxs-lookup"><span data-stu-id="04324-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="04324-112">Чтобы создать каталог конференций, используйте **кодлет New-CsConferenceDirectory.**</span><span class="sxs-lookup"><span data-stu-id="04324-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="04324-113">Например, следующая команда создает каталог конференций с идентификатором 42, который будет atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="04324-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="04324-114">Дополнительные сведения см. [в new-CsConferenceDirectory.](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="04324-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
