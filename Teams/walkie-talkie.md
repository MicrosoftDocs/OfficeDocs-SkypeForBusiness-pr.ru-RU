---
title: Приложение очень рация в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Настройка приложения очень рация в Microsoft Teams с точки зрения ITAdmin.
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
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043018"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="79974-103">Приложение очень рация в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79974-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="79974-104">Приложение очень рация в Teams предоставляет Мгновенное общение (PTT) для своей группы и вскоре станет доступно в общедоступной предварительной версии на Android.</span><span class="sxs-lookup"><span data-stu-id="79974-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and will soon be available in Public Preview on Android.</span></span> <span data-ttu-id="79974-105">Очень рация позволяет пользователям подключаться к своей команде с помощью тех же самых базовых каналов, в которых они находятся.</span><span class="sxs-lookup"><span data-stu-id="79974-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="79974-106">Только те пользователи, которые подключаются к очень рация в канале, становятся участниками и могут общаться друг с другом с помощью push-уведомлений по одной.</span><span class="sxs-lookup"><span data-stu-id="79974-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="79974-107">Благодаря очень рация в Teams пользователи могут безопасно общаться с знакомым PTT, не требуя выполнения массовых Радио, и очень рация, где бы вы ни находились в сети WiFi или сотовой связи с Интернетом.</span><span class="sxs-lookup"><span data-stu-id="79974-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="79974-108">Начало работы</span><span class="sxs-lookup"><span data-stu-id="79974-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="79974-109">Развертывание очень рация</span><span class="sxs-lookup"><span data-stu-id="79974-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="79974-110">В общедоступном предварительном просмотре очень рация не был предварительно установлен.</span><span class="sxs-lookup"><span data-stu-id="79974-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="79974-111">Чтобы включить эту функцию для пользователей в Организации, необходимо добавить очень рация в [политику настройки приложения](teams-app-setup-policies.md),   назначенную пользователям в [центре администрирования Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="79974-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="79974-112">После включения очень рация станет доступным в приложении Android в 48 часа.</span><span class="sxs-lookup"><span data-stu-id="79974-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="79974-113">Добавление очень рация в список приложений</span><span class="sxs-lookup"><span data-stu-id="79974-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="79974-114">В центре администрирования Microsoft Teams в разделе политики настройки **приложений Teams**необходимо  >  **Setup policies** **Разрешить закрепление пользователей** **на on**.</span><span class="sxs-lookup"><span data-stu-id="79974-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="79974-115">Затем в разделе закрепленные приложения нажмите кнопку **+ добавить приложения**.</span><span class="sxs-lookup"><span data-stu-id="79974-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Отображает раздел закрепленные приложения и выбранную кнопку "добавить приложения".":::

<span data-ttu-id="79974-117">На панели **Добавить закрепленные приложения** , которая отображается справа, используйте текстовое поле **Поиск** для поиска очень рация.</span><span class="sxs-lookup"><span data-stu-id="79974-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="79974-118">Когда вы попытаетесь найти результаты поиска, нажмите кнопку **Добавить** справа от имени, чтобы добавить ее в список.</span><span class="sxs-lookup"><span data-stu-id="79974-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Показана боковая панель "Добавление закрепленных приложений" с очень, введенная в область поиска и приложение очень рация в результатах поиска с кнопкой "Добавить" рядом с ней.":::

<span data-ttu-id="79974-120">Приложение очень рация должно отображаться в списке закрепленных приложений и доступно для использования после нажатия кнопки " **сохранить** ".</span><span class="sxs-lookup"><span data-stu-id="79974-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Список закрепленных приложений, добавленный приложением очень рация, и кнопка "Сохранить" под списком.":::

### <a name="network-documentation"></a><span data-ttu-id="79974-122">Сетевая документация</span><span class="sxs-lookup"><span data-stu-id="79974-122">Network documentation</span></span>

<span data-ttu-id="79974-123">Для обеспечения оптимального взаимодействия очень рация в Teams требуется подключение к Интернету, а ниже условия сети.</span><span class="sxs-lookup"><span data-stu-id="79974-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="79974-124">Задержка (RTT) < 300ms | Нарушение < 30ms | Потеря пакетов < 1%</span><span class="sxs-lookup"><span data-stu-id="79974-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="79974-125">Как отмечалось выше, качество мультимедиа в режиме реального времени через IP-сеть значительно влияет на качество сетевого подключения, но особенно в соответствии с количеством:</span><span class="sxs-lookup"><span data-stu-id="79974-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="79974-126">**Задержка** — это время, необходимое для получения IP-пакета от а до точки B в сети.</span><span class="sxs-lookup"><span data-stu-id="79974-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="79974-127">Эта задержка распространения сети по сути связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные накладные расходы, взятые различными маршрутизаторами между ними.</span><span class="sxs-lookup"><span data-stu-id="79974-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="79974-128">Задержка измеряется как время кругового приема-передачи (RTT).</span><span class="sxs-lookup"><span data-stu-id="79974-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="79974-129">**Потерь пакетов** — это часто определяется как процент пакетов, которые теряются в течение заданного окна.</span><span class="sxs-lookup"><span data-stu-id="79974-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="79974-130">Потери пакетов прямо влияют на качество звука — от небольшого до отдельных потерянных пакетов, которые практически не повлияли, для обратной связи между пределами, которые приводят к вырезке полного звука.</span><span class="sxs-lookup"><span data-stu-id="79974-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="79974-131">**Колебание** — это среднее значение задержки между последовательными пакетами.</span><span class="sxs-lookup"><span data-stu-id="79974-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="79974-132">Ожидаемое использование данных из очень рация — 20KB/s при отправке и получении звука.</span><span class="sxs-lookup"><span data-stu-id="79974-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="79974-133">При бездействии ожидается использование данных из очень рация незначительно.</span><span class="sxs-lookup"><span data-stu-id="79974-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="79974-134">Очень рация устройства</span><span class="sxs-lookup"><span data-stu-id="79974-134">Walkie Talkie devices</span></span>

<span data-ttu-id="79974-135">FirstLine работники часто должны говорить и получать очень рация звонки, даже когда их телефоны заблокированы.</span><span class="sxs-lookup"><span data-stu-id="79974-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="79974-136">Это возможно благодаря специальным устройствам с выделенной кнопкой PTT.</span><span class="sxs-lookup"><span data-stu-id="79974-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="79974-137">Существующие телефоны</span><span class="sxs-lookup"><span data-stu-id="79974-137">Existing phones</span></span>
  - <span data-ttu-id="79974-138">Проводная гарнитура ([Klein](https://www.kleinelectronics.com/))</span><span class="sxs-lookup"><span data-stu-id="79974-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/))</span></span>
  - <span data-ttu-id="79974-139">Беспроводные гарнитуры ([Jabra BlueParrott](https://www.blueparrott.com/))</span><span class="sxs-lookup"><span data-stu-id="79974-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/))</span></span>
- <span data-ttu-id="79974-140">Микрофонныхные телефоны</span><span class="sxs-lookup"><span data-stu-id="79974-140">Rugged phones</span></span>
  - <span data-ttu-id="79974-141">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="79974-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="79974-142">[Дополнительные сведения](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="79974-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="79974-143">[Руководство по настройке](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span><span class="sxs-lookup"><span data-stu-id="79974-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="79974-144">Эти устройства не сертифицированы Teams.</span><span class="sxs-lookup"><span data-stu-id="79974-144">These devices are not Teams certified.</span></span> <span data-ttu-id="79974-145">Они были проверены для работы с Teams очень рация.</span><span class="sxs-lookup"><span data-stu-id="79974-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="79974-146">Требования к лицензии</span><span class="sxs-lookup"><span data-stu-id="79974-146">License requirements</span></span>

<span data-ttu-id="79974-147">Приложение очень рация входит в комплект [подписки на Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)для всех платных лицензий на Teams.</span><span class="sxs-lookup"><span data-stu-id="79974-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="79974-148">Дополнительные сведения о [том, как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b), можно узнать в разделе Получение доступа к Teams</span><span class="sxs-lookup"><span data-stu-id="79974-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="79974-149">Для использования некоторых расширенных функций может потребоваться дополнительное лицензирование.</span><span class="sxs-lookup"><span data-stu-id="79974-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="79974-150">Например, для интеграции с Samsung Galaxy XCover Pro требуется лицензия на использование Knox.</span><span class="sxs-lookup"><span data-stu-id="79974-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="79974-151">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="79974-151">Further information</span></span>

- <span data-ttu-id="79974-152">ITAdmins может поддерживать управление тем, кто использует очень рация через политики приложений.</span><span class="sxs-lookup"><span data-stu-id="79974-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="79974-153">Если ваш сотрудник Firstline использует мобильные данные для общения с помощью Teams, очень рация будет использовать один и тот же метод.</span><span class="sxs-lookup"><span data-stu-id="79974-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="79974-154">Очень рация лучше подойдет для ситуаций, связанных с пропускной способностью, или ситуаций, когда ваш смартфон подключен и работает.</span><span class="sxs-lookup"><span data-stu-id="79974-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="79974-155">Очень рация не работает, если вы не подключены вообще.</span><span class="sxs-lookup"><span data-stu-id="79974-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="79974-156">Дополнительные сведения о том, как работать с конечным пользователем, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="79974-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="79974-157">Начало работы с Teams очень рация</span><span class="sxs-lookup"><span data-stu-id="79974-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="79974-158">Общайтесь с коллегами с помощью очень рация</span><span class="sxs-lookup"><span data-stu-id="79974-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
