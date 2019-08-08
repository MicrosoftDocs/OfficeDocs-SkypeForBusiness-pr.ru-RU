---
title: Просмотр записей использования PSTN в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Сводка: сведения о том, как просматривать записи об использовании PSTN с помощью панели управления "Skype для бизнеса Server" или в командной консоли Skype для бизнеса Server.'
ms.openlocfilehash: bbc9b7f174ff4b6710009af47dbdcd20e12334d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240002"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="e3141-103">Просмотр записей использования PSTN в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e3141-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="e3141-104">**Сводка:** Сведения о том, как просматривать записи об использовании PSTN с помощью панели управления "Skype для бизнеса Server" или в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e3141-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="e3141-p101">В записи об использовании ТСОП указывается класс вызова (например, внутренний, локальный вызов или вызов на дальние расстояния), который может выполняться различными пользователями или группами пользователей в организации. Для получения дополнительных сведений см. [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e3141-p101">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization. For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e3141-107">Просмотр записи использования PSTN с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3141-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e3141-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e3141-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="e3141-109">На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем — **Использование ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="e3141-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="e3141-110">На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="e3141-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3141-111">На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e3141-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="e3141-112">Просмотр сведений об использовании PSTN с помощью командлетов командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3141-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="e3141-113">Чтобы просмотреть сведения о всех используемых КТСОП, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e3141-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="e3141-114">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="e3141-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="e3141-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e3141-115">See also</span></span>

[<span data-ttu-id="e3141-116">Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e3141-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

