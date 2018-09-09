---
title: Просмотр записей использования ТСОП в Скайп для бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Сводка: Узнайте, как для просмотра записей использования ТСОП Скайп для или с помощью панели управления сервера Business Скайп для консоли Business Server.'
ms.openlocfilehash: 7b058ea2d45683c7ca59e34f65372857df791d76
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888644"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="9bd3e-103">Просмотр записей использования ТСОП в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9bd3e-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="9bd3e-104">**Сводка:** Узнайте, как просматривать записи использования ТСОП Скайп для или с помощью панели управления сервера Business Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bd3e-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="9bd3e-105">Запись режима работы с общей переключения телефонной сети общего пользования (PSTN) задает класс вызовов (например, внутренний, локальный или междугородных), которые могут выполняться разными пользователями или группами пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="9bd3e-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="9bd3e-106">Дополнительные сведения см в документации по планированию [Работы с ТСОП](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9bd3e-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9bd3e-107">Просмотр записи об использовании ТСОП с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="9bd3e-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9bd3e-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bd3e-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="9bd3e-109">На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем — **Использование ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="9bd3e-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="9bd3e-110">На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="9bd3e-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9bd3e-111">На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9bd3e-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="9bd3e-112">Чтобы просмотреть сведения об использовании ТСОП с помощью Скайп для командлетов командной консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="9bd3e-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="9bd3e-113">Чтобы просмотреть сведения об использовании ТСОП, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="9bd3e-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="9bd3e-114">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="9bd3e-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="9bd3e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9bd3e-115">See also</span></span>

[<span data-ttu-id="9bd3e-116">Создание или изменение политики голосовой связи и Настройка записей использования ТСОП в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9bd3e-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

