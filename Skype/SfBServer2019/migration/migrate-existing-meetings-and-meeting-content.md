---
title: Перенос существующих собраний и содержимого собраний
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'При перемещении учетной записи пользователя на сервер Skype для бизнеса Server 2019 с этой учетной записью переносятся следующие сведения:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288602"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="8e2f8-103">Перенос существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="8e2f8-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="8e2f8-104">При перемещении учетной записи пользователя на сервер 2019 в Skype для бизнеса Server с учетной записью пользователя переносятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="8e2f8-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="8e2f8-105">**Собрания, уже запланированные пользователем**.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="8e2f8-106">Сюда входит перемещение каталогов конференций и данных конференций.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="8e2f8-107">**Персональный идентификационный номер пользователя (ПИН-код)**.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="8e2f8-108">Текущий ПИН-код пользователя продолжает работать, пока не истечет срок действия или пользователь запросит новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="8e2f8-109">Указанные ниже сведения об учетной записи пользователя не перемещаются на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="8e2f8-110">**Содержимое собрания**.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-110">**Meeting content**.</span></span> <span data-ttu-id="8e2f8-111">Чтобы переместить содержимое, совместно используемое во время собрания, например PowerPoint, доска, вложения или данные опроса, используйте параметр **-мовеконференцедата** в составе командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="8e2f8-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

