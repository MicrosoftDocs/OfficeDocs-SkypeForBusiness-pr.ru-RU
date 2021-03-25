---
title: Просмотр записей использования PSTN в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: Сводка. Узнайте, как просматривать записи использования PSTN с помощью панели управления Skype для бизнес-серверов или оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109835"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="57648-103">Просмотр записей использования PSTN в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="57648-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="57648-104">**Сводка:** Узнайте, как просматривать записи использования PSTN с помощью панели управления Skype для бизнес-серверов или оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="57648-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="57648-105">Запись использования общедоступных переключений телефонной сети (PSTN) указывает класс вызова (например, внутренний, локальный или междугородний), который может быть выполнен различными пользователями или группами пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="57648-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="57648-106">Подробные сведения [см.](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="57648-106">For details, see [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="57648-107">Просмотр записи использования PSTN с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="57648-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="57648-108">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="57648-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="57648-109">На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем щелкните **Использование ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="57648-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="57648-110">На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="57648-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57648-111">На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="57648-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="57648-112">Просмотр сведений об использовании PSTN с помощью команды Skype для управления бизнес-серверами</span><span class="sxs-lookup"><span data-stu-id="57648-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="57648-113">Чтобы просмотреть сведения обо всех ваших приложениях PSTN, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="57648-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="57648-114">Эта команда возвращает следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="57648-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="57648-115">См. также</span><span class="sxs-lookup"><span data-stu-id="57648-115">See also</span></span>

[<span data-ttu-id="57648-116">Создание или изменение голосовой политики и настройка записей использования PSTN в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="57648-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)