---
title: Перенос существующих собраний и содержимое собраний
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Когда учетная запись пользователя перемещается из Скайп для сервера Business Server 2019, с учетной записью пользователя перемещается следующая информация:'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030373"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="f7d37-103">Перенос существующих собраний и содержимое собраний</span><span class="sxs-lookup"><span data-stu-id="f7d37-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="f7d37-104">При перемещении учетной записи пользователя Скайп для сервера Business Server 2019 с учетной записью пользователя перемещается следующая информация:</span><span class="sxs-lookup"><span data-stu-id="f7d37-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="f7d37-105">**Собрания, уже запланированных пользователем**.</span><span class="sxs-lookup"><span data-stu-id="f7d37-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="f7d37-106">Этот компонент включает перемещение каталогов конференций и данных конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f7d37-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="f7d37-107">**Пользователя персональный идентификационный номер (ПИН-кода)**.</span><span class="sxs-lookup"><span data-stu-id="f7d37-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="f7d37-108">Текущий ПИН-код пользователя продолжает работать до истечения срока действия или пользователь запрашивает новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="f7d37-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="f7d37-109">Следующие сведения учетной записи пользователя не перемещается на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="f7d37-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="f7d37-110">**Контенту собрания**.</span><span class="sxs-lookup"><span data-stu-id="f7d37-110">**Meeting content**.</span></span> <span data-ttu-id="f7d37-111">Для перемещения содержимого, совместно используемого во время собрания, например, PowerPoint, доски, вложений и данных опроса, используйте параметр **- MoveConferenceData** как часть командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="f7d37-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

