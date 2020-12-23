---
title: Приложение Walkie Talkie в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Настройка приложения Walkie Talkie в Microsoft Teams с точки зрения ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 605ba58582210c71561cd60442aa66f97be0be0d
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262506"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="391d8-103">Приложение Walkie Talkie в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="391d8-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="391d8-104">Приложение Walkie Talkie в Teams позволяет мгновенно общаться с командой с помощью push-to-talk (PTT), и теперь доступно для Android.</span><span class="sxs-lookup"><span data-stu-id="391d8-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="391d8-105">Скайти Talkie позволяет пользователям связываться со своей командой, используя каналы, в которые они являются.</span><span class="sxs-lookup"><span data-stu-id="391d8-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="391d8-106">Только пользователи, которые подключаются к Walkie Talkie в канале, становятся участниками и могут общаться друг с другом по одной.</span><span class="sxs-lookup"><span data-stu-id="391d8-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="391d8-107">С помощью Walkie Talkie в Teams сотрудники, работающие без компьютеров, теперь могут безопасно взаимодействовать с привычным взаимодействием с PTT, не утомив при этом массовые радиосвязи, а Лидия Talkie работает где угодно с Wi-Fi или мобильным подключением к Интернету.</span><span class="sxs-lookup"><span data-stu-id="391d8-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="391d8-108">Начало работы</span><span class="sxs-lookup"><span data-stu-id="391d8-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="391d8-109">Развертывание Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="391d8-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="391d8-110">В настоящее время приложение Walkie Talkie не предварительно установлено.</span><span class="sxs-lookup"><span data-stu-id="391d8-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="391d8-111">Чтобы включить эту функцию для пользователей в организации, необходимо [](teams-app-setup-policies.md)добавить Вадию Talkie в политику установки приложений, назначенную пользователям в Центре администрирования   [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="391d8-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="391d8-112">После включения Walkie Talkie станет доступно в приложении для Android в течение 48 часов.</span><span class="sxs-lookup"><span data-stu-id="391d8-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="391d8-113">Добавление в список приложений Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="391d8-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="391d8-114">В Центре администрирования Microsoft Teams в соответствии с политиками настройки приложений **Teams** необходимо установить для пользователя режим "Разрешить закрепление".  >    </span><span class="sxs-lookup"><span data-stu-id="391d8-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="391d8-115">Затем в разделе "Закрепленные приложения" нажмите **кнопку +Добавить приложения.**</span><span class="sxs-lookup"><span data-stu-id="391d8-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Раздел "Закрепленные приложения" и выбранная кнопка "Добавить приложения".":::

<span data-ttu-id="391d8-117">На панели **"Добавление** закрепленных приложений", которая  появляется справа, найдите в текстовом окне "Поиск" Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="391d8-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="391d8-118">Если это результат поиска, нажмите  кнопку "Добавить" справа от имени, чтобы добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="391d8-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Отображает боковую панель "Добавить закрепленные приложения" с введенной в области поиска и приложением Walkie Talkie в результатах поиска с кнопкой "Добавить" рядом с ней.":::

<span data-ttu-id="391d8-120">Приложение Walkie Talkie должно появиться в списке закрепленных приложений и стать доступно для использования после нажатия кнопки **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="391d8-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Список закрепленных приложений с добавленным приложением Walkie Talkie и кнопкой "Сохранить" под списком.":::

### <a name="network-documentation"></a><span data-ttu-id="391d8-122">Сетевая документация</span><span class="sxs-lookup"><span data-stu-id="391d8-122">Network documentation</span></span>

<span data-ttu-id="391d8-123">Для обеспечения оптимального взаимодействия требуется подключение к Интернету, а для оптимальной работы требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="391d8-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="391d8-124">Показатель</span><span class="sxs-lookup"><span data-stu-id="391d8-124">Metric</span></span> | <span data-ttu-id="391d8-125">Обязательный</span><span class="sxs-lookup"><span data-stu-id="391d8-125">Required</span></span> |
|---|---|
|<span data-ttu-id="391d8-126">Задержка (RTT)</span><span class="sxs-lookup"><span data-stu-id="391d8-126">Latency (RTT)</span></span> | <span data-ttu-id="391d8-127">< 300 мс</span><span class="sxs-lookup"><span data-stu-id="391d8-127">< 300ms</span></span> |
|<span data-ttu-id="391d8-128">Искажение</span><span class="sxs-lookup"><span data-stu-id="391d8-128">Jitter</span></span> |<span data-ttu-id="391d8-129">< 30 мс</span><span class="sxs-lookup"><span data-stu-id="391d8-129">< 30ms</span></span> |
|<span data-ttu-id="391d8-130">Packet Loss (Потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="391d8-130">Packet Loss</span></span> |<span data-ttu-id="391d8-131">< 1 %</span><span class="sxs-lookup"><span data-stu-id="391d8-131">< 1%</span></span> |

<span data-ttu-id="391d8-132">Как было отмечено выше, на качество мультимедиа в режиме реального времени по IP-сети в значительной мере влияет качество сетевого подключения, но особенно на количество:</span><span class="sxs-lookup"><span data-stu-id="391d8-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="391d8-133">**Задержка —** это время, необходимое для получения IP-пакета из точки A в точку B сети.</span><span class="sxs-lookup"><span data-stu-id="391d8-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="391d8-134">Эта задержка распространения сети, по существу, связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные накладные расходы, которые связаны с различными маршрутизаторами между ними.</span><span class="sxs-lookup"><span data-stu-id="391d8-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="391d8-135">Задержка измеряется как время кругового пути (RTT).</span><span class="sxs-lookup"><span data-stu-id="391d8-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="391d8-136">**Packet Loss** (Потеря пакетов) — часто определяется как процент пакетов, потерянных за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="391d8-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="391d8-137">Потеря пакетов напрямую влияет на качество звука — небольшие потерянные пакеты практически не оказывают влияния, а потери пакетов в очереди приводят к полному из-за разрыва звука.</span><span class="sxs-lookup"><span data-stu-id="391d8-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="391d8-138">**Дрожание** — это среднее изменение задержки между последовательными пакетами.</span><span class="sxs-lookup"><span data-stu-id="391d8-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="391d8-139">Ожидаемое использование данных от Walkie Talkie составляет около 20 КБ/с при отправке или получении звука.</span><span class="sxs-lookup"><span data-stu-id="391d8-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="391d8-140">Если данные неаемые, ожидаемый объем данных, полученный от Walkie Talkie, является неосторожным.</span><span class="sxs-lookup"><span data-stu-id="391d8-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="391d8-141">Устройства Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="391d8-141">Walkie Talkie devices</span></span>

<span data-ttu-id="391d8-142">Сотрудникам, работающим с firstline, часто приходится общаться и принимать звонки Walkie Talkie, даже если их телефоны заблокированы.</span><span class="sxs-lookup"><span data-stu-id="391d8-142">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="391d8-143">Такая возможность возможна на специализированных устройствах со специальной кнопкой PTT.</span><span class="sxs-lookup"><span data-stu-id="391d8-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="391d8-144">Гарнитуры</span><span class="sxs-lookup"><span data-stu-id="391d8-144">Headsets</span></span>
  - <span data-ttu-id="391d8-145">Проводные гарнитуры[(Electronic Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)</span><span class="sxs-lookup"><span data-stu-id="391d8-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="391d8-146">Беспроводные гарнитуры[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)</span><span class="sxs-lookup"><span data-stu-id="391d8-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="391d8-147">Неровные телефоны</span><span class="sxs-lookup"><span data-stu-id="391d8-147">Rugged phones</span></span>
  - <span data-ttu-id="391d8-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="391d8-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="391d8-149">[Дополнительные сведения.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)</span><span class="sxs-lookup"><span data-stu-id="391d8-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="391d8-150">[Руководство по настройке.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)</span><span class="sxs-lookup"><span data-stu-id="391d8-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="391d8-151">Эти устройства не сертифицированы для Teams.</span><span class="sxs-lookup"><span data-stu-id="391d8-151">These devices are not Teams certified.</span></span> <span data-ttu-id="391d8-152">Они были проверены для работы с Командой Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="391d8-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="391d8-153">Требования к лицензии</span><span class="sxs-lookup"><span data-stu-id="391d8-153">License requirements</span></span>

<span data-ttu-id="391d8-154">Приложение Walkie Talkie включено во все платные лицензии Teams в [подписках на Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)</span><span class="sxs-lookup"><span data-stu-id="391d8-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="391d8-155">Дополнительные сведения о получении Teams: как получить доступ [к Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="391d8-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="391d8-156">Для некоторых дополнительных функций может потребоваться дополнительное лицензирование.</span><span class="sxs-lookup"><span data-stu-id="391d8-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="391d8-157">Например, для интеграции с Samsung Galaxy XCover Pro требуется лицензия Knox.</span><span class="sxs-lookup"><span data-stu-id="391d8-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="391d8-158">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="391d8-158">Further information</span></span>

- <span data-ttu-id="391d8-159">ИТ-политики могут управлять тем, кто использует Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="391d8-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="391d8-160">Если ваш сотрудник без компьютеров использует мобильные данные для связи через Teams, Walkie Talkie будет использовать тот же метод.</span><span class="sxs-lookup"><span data-stu-id="391d8-160">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="391d8-161">Walkie Talkie должна хорошо работать в ситуациях, связанных с низкой пропускной способностью, или в ситуациях, когда смартфон подключен и работает.</span><span class="sxs-lookup"><span data-stu-id="391d8-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="391d8-162">Если нет подключения, walkie Talkie не будет работать.</span><span class="sxs-lookup"><span data-stu-id="391d8-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="391d8-163">Дополнительные статью о интерфейсе пользователя см. в:</span><span class="sxs-lookup"><span data-stu-id="391d8-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="391d8-164">Начало работы с Командой Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="391d8-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="391d8-165">Общение с командой с помощью Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="391d8-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
