---
title: Перенос существующих собраний и содержимого собраний
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Когда учетная запись пользователя перемещается из Скайп для сервера Business Server 2019, с учетной записью пользователя перемещается следующая информация:'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231660"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="edf6c-103">Перенос существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="edf6c-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="edf6c-104">При перемещении учетной записи пользователя Скайп для сервера Business Server 2019 с учетной записью пользователя перемещается следующая информация:</span><span class="sxs-lookup"><span data-stu-id="edf6c-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="edf6c-105">**Собрания, уже запланированных пользователем**.</span><span class="sxs-lookup"><span data-stu-id="edf6c-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="edf6c-106">Этот компонент включает перемещение каталогов конференций и данных конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="edf6c-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="edf6c-107">**Пользователя персональный идентификационный номер (ПИН-кода)**.</span><span class="sxs-lookup"><span data-stu-id="edf6c-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="edf6c-108">Текущий ПИН-код пользователя продолжает работать до истечения срока действия или пользователь запрашивает новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="edf6c-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="edf6c-109">Следующие сведения учетной записи пользователя не перемещается на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="edf6c-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="edf6c-110">**Контенту собрания**.</span><span class="sxs-lookup"><span data-stu-id="edf6c-110">**Meeting content**.</span></span> <span data-ttu-id="edf6c-111">Для перемещения содержимого, совместно используемого во время собрания, например, PowerPoint, доски, вложений и данных опроса, используйте параметр **- MoveConferenceData** как часть командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="edf6c-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

