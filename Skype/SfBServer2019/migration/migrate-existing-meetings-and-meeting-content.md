---
title: Перенос существующих собраний и содержимого собраний
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Когда учетная запись пользователя перемещается на сервер Skype для бизнеса Server 2019, следующая информация перемещается вместе с этой учетной записью пользователя:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752691"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="45e2c-103">Перенос существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="45e2c-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="45e2c-104">Когда учетная запись пользователя перемещается на сервер Skype для бизнеса Server 2019, следующая информация перемещается вместе с этой учетной записью пользователя:</span><span class="sxs-lookup"><span data-stu-id="45e2c-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="45e2c-105">**Собрания, уже запланированные этим пользователем**.</span><span class="sxs-lookup"><span data-stu-id="45e2c-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="45e2c-106">В том числе, перемещаются каталоги конференций и данные конференций.</span><span class="sxs-lookup"><span data-stu-id="45e2c-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="45e2c-107">**Персональный идентификационный номер пользователя (ПИН-код)**.</span><span class="sxs-lookup"><span data-stu-id="45e2c-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="45e2c-108">Текущий ПИН-код пользователя продолжает работать, пока не истечет срок его действия или пользователь запросит новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="45e2c-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="45e2c-109">На новый сервер не перемещаются следующие сведения об учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="45e2c-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="45e2c-110">**Содержимое собрания**.</span><span class="sxs-lookup"><span data-stu-id="45e2c-110">**Meeting content**.</span></span> <span data-ttu-id="45e2c-111">Чтобы переместить контент, совместно используемый во время собрания, например PowerPoint, доска, вложения или данные опроса, используйте параметр **– мовеконференцедата** в составе командлета **Move – CsUser** .</span><span class="sxs-lookup"><span data-stu-id="45e2c-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

