---
title: Приложение "Рация" в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Как настроить приложение "Рация" в Microsoft Teams с точки зрения ИТ-администратора.
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
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479076"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="147cc-103">Приложение "Рация" в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="147cc-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="147cc-104">Приложение "Рация" в Teams обеспечивает для вашей команды оперативную связь путем "разговора нажатием" и теперь доступно на Android.</span><span class="sxs-lookup"><span data-stu-id="147cc-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="147cc-105">С помощью рации пользователи в команде могут общаться друг с другом, используя те же каналы, в которых они участвуют.</span><span class="sxs-lookup"><span data-stu-id="147cc-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="147cc-106">Только пользователи, которые подключились к рации в канале, становятся участниками разговора и могут говорить друг с другом по очереди.</span><span class="sxs-lookup"><span data-stu-id="147cc-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="147cc-107">Рация в Teams позволяет сотрудникам без компьютеров безопасно общаться друг с другом, как они привыкли это делать, но не нося с собой громоздкие переговорные устройства. Рация работает везде, где есть доступ к Интернету через Wi-Fi или сотовое подключение.</span><span class="sxs-lookup"><span data-stu-id="147cc-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="147cc-108">Начало работы</span><span class="sxs-lookup"><span data-stu-id="147cc-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="147cc-109">Развертывание рации</span><span class="sxs-lookup"><span data-stu-id="147cc-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="147cc-110">В настоящее время walkie Talkie доступен для устройств с Android с Google мобильные службы (GMS) и не предварительно установлен.</span><span class="sxs-lookup"><span data-stu-id="147cc-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="147cc-111">Чтобы включить эту функцию для пользователей в вашей организации, добавьте приложение "Рация" в  [политику установки приложений](teams-app-setup-policies.md) , назначенную пользователям в [Центре администрирования Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="147cc-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="147cc-112">После включения рация в течение 48 часов станет доступна в приложении для Android.</span><span class="sxs-lookup"><span data-stu-id="147cc-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="147cc-113">Добавление рации в список приложений</span><span class="sxs-lookup"><span data-stu-id="147cc-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="147cc-114">В Центре администрирования Microsoft Teams выберите **Приложение Teams** > **Политики установки** и установите для параметра **Разрешить пользователям закрепление** значение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="147cc-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="147cc-115">Затем в разделе "Закрепленные приложения" нажмите кнопку **+Добавить приложения**.</span><span class="sxs-lookup"><span data-stu-id="147cc-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Показаны раздел "Закрепленные приложения" и нажимаемая кнопка "Добавить приложения".":::

<span data-ttu-id="147cc-117">На панели **Добавить закрепленные приложения** справа поищите приложение "Рация" в текстовом поле **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="147cc-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="147cc-118">Если она есть в результатах  поиска, выберите кнопку Добавить справа от имени, чтобы добавить ее в список.</span><span class="sxs-lookup"><span data-stu-id="147cc-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Показаны боковая панель "Добавить закрепленные приложения" с введенным в область поиска названием "Рация", приложение "Рация" в результатах поиска и кнопка "Добавить" рядом с ним.":::

<span data-ttu-id="147cc-120">Теперь приложение "Рация" должно появиться в списке закрепленных приложений и будет доступно для использования после нажатия кнопки **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="147cc-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Показан список закрепленных приложений с добавленным приложением "Рация" и кнопкой "Сохранить" под списком.":::

### <a name="network-documentation"></a><span data-ttu-id="147cc-122">Сетевая документация</span><span class="sxs-lookup"><span data-stu-id="147cc-122">Network documentation</span></span>

<span data-ttu-id="147cc-123">Для использования рации в Teams требуется подключение к Интернету, а условия сети, необходимые для оптимальной работы, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="147cc-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="147cc-124">Показатель</span><span class="sxs-lookup"><span data-stu-id="147cc-124">Metric</span></span> | <span data-ttu-id="147cc-125">Обязательно</span><span class="sxs-lookup"><span data-stu-id="147cc-125">Required</span></span> |
|---|---|
|<span data-ttu-id="147cc-126">Задержка (RTT)</span><span class="sxs-lookup"><span data-stu-id="147cc-126">Latency (RTT)</span></span> | <span data-ttu-id="147cc-127">< 300 мс</span><span class="sxs-lookup"><span data-stu-id="147cc-127">< 300ms</span></span> |
|<span data-ttu-id="147cc-128">Дрожание</span><span class="sxs-lookup"><span data-stu-id="147cc-128">Jitter</span></span> |<span data-ttu-id="147cc-129">< 30 мс</span><span class="sxs-lookup"><span data-stu-id="147cc-129">< 30ms</span></span> |
|<span data-ttu-id="147cc-130">Потеря пакетов</span><span class="sxs-lookup"><span data-stu-id="147cc-130">Packet Loss</span></span> |<span data-ttu-id="147cc-131">< 1 %</span><span class="sxs-lookup"><span data-stu-id="147cc-131">< 1%</span></span> |

<span data-ttu-id="147cc-132">Как указано выше, на качество мультимедиа в реальном времени по IP-сети значительно влияет качество сетевого подключения, но в особенности следующие показатели:</span><span class="sxs-lookup"><span data-stu-id="147cc-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="147cc-133">**Задержка** — это время, необходимое для передачи IP-пакета из точки A в точку B в сети.</span><span class="sxs-lookup"><span data-stu-id="147cc-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="147cc-134">Эта задержка распространения по сети, по сути, связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные накладные расходы различных между ними маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="147cc-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="147cc-135">Задержка измеряется как период кругового обращения (RTT).</span><span class="sxs-lookup"><span data-stu-id="147cc-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="147cc-136">**Дрожание между** прибытиями — это среднее изменение задержки между последовательными пакетами.</span><span class="sxs-lookup"><span data-stu-id="147cc-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="147cc-137">**Потеря пакетов** — часто определяется как процент пакетов, которые теряются за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="147cc-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="147cc-138">Потеря пакетов напрямую влияет на качество звука — отдельные потерянные пакеты почти не оказывают влияния, а сплошные последовательные потери приводят к полному исчезновению звука.</span><span class="sxs-lookup"><span data-stu-id="147cc-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="147cc-139">Ожидаемое использование данных в walkie Talkie составляет около 20 КБ/с при отправке или получении звука.</span><span class="sxs-lookup"><span data-stu-id="147cc-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="147cc-140">При простое ожидаемой интенсивностью использования данных в рации можно пренебречь.</span><span class="sxs-lookup"><span data-stu-id="147cc-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="147cc-141">Устройства для рации</span><span class="sxs-lookup"><span data-stu-id="147cc-141">Walkie Talkie devices</span></span>

<span data-ttu-id="147cc-142">Сотрудникам без компьютеров часто приходится говорить и принимать вызовы по рации, даже когда их телефоны заблокированы.</span><span class="sxs-lookup"><span data-stu-id="147cc-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="147cc-143">Этот режим работы реализуется на специальных устройствах с кнопкой передачи.</span><span class="sxs-lookup"><span data-stu-id="147cc-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="147cc-144">**Гарнитуры**</span><span class="sxs-lookup"><span data-stu-id="147cc-144">**Headsets**</span></span>
  - <span data-ttu-id="147cc-145">Беспроводные гарнитуры</span><span class="sxs-lookup"><span data-stu-id="147cc-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="147cc-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="147cc-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="147cc-147">Проводные гарнитуры</span><span class="sxs-lookup"><span data-stu-id="147cc-147">Wired headsets</span></span> 
    - [<span data-ttu-id="147cc-148">Klein Electronics</span><span class="sxs-lookup"><span data-stu-id="147cc-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="147cc-149">**Прочные телефоны**</span><span class="sxs-lookup"><span data-stu-id="147cc-149">**Rugged phones**</span></span>
  - <span data-ttu-id="147cc-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="147cc-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="147cc-151">Ручная настройка. Teams, перейдите к Параметры > дополнительным функциям > XCover/Active.</span><span class="sxs-lookup"><span data-stu-id="147cc-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="147cc-152">Включит клавишу CONTROL XCover с приложением и выберите "Teams"</span><span class="sxs-lookup"><span data-stu-id="147cc-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="147cc-153">Настройка MDM</span><span class="sxs-lookup"><span data-stu-id="147cc-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="147cc-154">Эти устройства не сертифицированы для Teams.</span><span class="sxs-lookup"><span data-stu-id="147cc-154">These devices are not Teams certified.</span></span> <span data-ttu-id="147cc-155">Они прошли проверку на работу с рацией Teams.</span><span class="sxs-lookup"><span data-stu-id="147cc-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="147cc-156">Требования к лицензиям</span><span class="sxs-lookup"><span data-stu-id="147cc-156">License requirements</span></span>

<span data-ttu-id="147cc-157">Приложение "Рация" включено во все платные лицензии Teams в [подписках на Office 365](/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="147cc-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="147cc-158">Чтобы больше узнать о получении Teams, обратитесь к статье  [Как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="147cc-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="147cc-159">Для некоторых функций могут потребоваться дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="147cc-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="147cc-160">Например, для интеграции с Samsung Galaxy XCover Pro требуется лицензия Knox.</span><span class="sxs-lookup"><span data-stu-id="147cc-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="147cc-161">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="147cc-161">Further information</span></span>

- <span data-ttu-id="147cc-162">ИТ-администраторы могут контролировать использование рации с помощью политик приложений.</span><span class="sxs-lookup"><span data-stu-id="147cc-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="147cc-163">Если ваш сотрудник без компьютера переднего телефона использует для связи с помощью Teams мобильные данные, этот же метод будет использоваться и для рации.</span><span class="sxs-lookup"><span data-stu-id="147cc-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="147cc-164">Рация хорошо работает в ситуациях с малой пропускной способностью или в ситуациях, когда смартфон подключен и работает.</span><span class="sxs-lookup"><span data-stu-id="147cc-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="147cc-165">Если подключения нет, рация не будет работать.</span><span class="sxs-lookup"><span data-stu-id="147cc-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="147cc-166">Дополнительно о работе конечных пользователей можно прочитать в статьях</span><span class="sxs-lookup"><span data-stu-id="147cc-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="147cc-167">Начало работы с рацией Teams</span><span class="sxs-lookup"><span data-stu-id="147cc-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="147cc-168">Связь с командой при помощи рации</span><span class="sxs-lookup"><span data-stu-id="147cc-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
