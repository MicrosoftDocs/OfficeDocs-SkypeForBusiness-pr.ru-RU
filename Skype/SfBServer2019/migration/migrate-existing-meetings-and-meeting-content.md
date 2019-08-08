---
title: Перенос существующих собраний и содержимого собраний
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'При перемещении учетной записи пользователя на сервер Skype для бизнеса Server 2019 с этой учетной записью переносятся следующие сведения:'
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238000"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="0eca6-103">Перенос существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="0eca6-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="0eca6-104">При перемещении учетной записи пользователя на сервер 2019 в Skype для бизнеса Server с учетной записью пользователя переносятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0eca6-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="0eca6-105">**Собрания, уже запланированные пользователем**.</span><span class="sxs-lookup"><span data-stu-id="0eca6-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="0eca6-106">Сюда входит перемещение каталогов конференций и данных конференций.</span><span class="sxs-lookup"><span data-stu-id="0eca6-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="0eca6-107">**Персональный идентификационный номер пользователя (ПИН-код)**.</span><span class="sxs-lookup"><span data-stu-id="0eca6-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="0eca6-108">Текущий ПИН-код пользователя продолжает работать, пока не истечет срок действия или пользователь запросит новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="0eca6-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="0eca6-109">Указанные ниже сведения об учетной записи пользователя не перемещаются на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="0eca6-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="0eca6-110">**Содержимое собрания**.</span><span class="sxs-lookup"><span data-stu-id="0eca6-110">**Meeting content**.</span></span> <span data-ttu-id="0eca6-111">Чтобы переместить содержимое, совместно используемое во время собрания, например PowerPoint, доска, вложения или данные опроса, используйте параметр **-мовеконференцедата** в составе командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="0eca6-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

