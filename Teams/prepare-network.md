---
title: Подготовка сети организации к использованию Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Узнайте о подготовке сети организации к использованию Microsoft Teams, включая требования к сети, оптимизацию сети и требования к пропускной способности.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420834"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="f8fa9-103">Подготовка сети организации к использованию Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="f8fa9-104">Требования к сети</span><span class="sxs-lookup"><span data-stu-id="f8fa9-104">Network requirements</span></span>

<span data-ttu-id="f8fa9-105">Если вы уже [оптимизировали сеть для Microsoft 365 или Office 365](/Office365/Enterprise/assessing-network-connectivity), вероятно, вы уже готовы к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="f8fa9-106">Как бы то ни было, в особенности если вы быстро развертываете Teams в качестве первой нагрузки Microsoft 365 или Office 365 для поддержки **удаленных работников**, проверьте следующее перед началом развертывания Teams:</span><span class="sxs-lookup"><span data-stu-id="f8fa9-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="f8fa9-107">Во всех ли расположениях вашей организации есть доступ к Интернету (для подключения к Microsoft 365 или Office 365)?</span><span class="sxs-lookup"><span data-stu-id="f8fa9-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="f8fa9-108">В дополнение к обычному веб-трафику, убедитесь, что вы открыли TCP-порты и IP-адреса, перечисленные для Teams в статье [URL-адреса и диапазоны IP-адресов Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f8fa9-109">Если нужно настроить федерацию со Skype для бизнеса в локальной среде или через Интернет, потребуется настроить дополнительную запись DNS.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="f8fa9-110">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="f8fa9-110">DNS record</span></span>  |<span data-ttu-id="f8fa9-111">Служба</span><span class="sxs-lookup"><span data-stu-id="f8fa9-111">Service</span></span>  |<span data-ttu-id="f8fa9-112">Protocol (Протокол)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-112">Protocol</span></span>  |<span data-ttu-id="f8fa9-113">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-113">Priority</span></span>  |<span data-ttu-id="f8fa9-114">Weight  (Вес)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-114">Weight</span></span>  |<span data-ttu-id="f8fa9-115">Port (Порт)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-115">Port</span></span>  |<span data-ttu-id="f8fa9-116">Target (Назначение)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="f8fa9-117">SRV</span><span class="sxs-lookup"><span data-stu-id="f8fa9-117">SRV</span></span>     |<span data-ttu-id="f8fa9-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f8fa9-118">sipfederationtls</span></span>     |<span data-ttu-id="f8fa9-119">TCP</span><span class="sxs-lookup"><span data-stu-id="f8fa9-119">TCP</span></span>     |<span data-ttu-id="f8fa9-120">100</span><span class="sxs-lookup"><span data-stu-id="f8fa9-120">100</span></span>     |<span data-ttu-id="f8fa9-121">1</span><span class="sxs-lookup"><span data-stu-id="f8fa9-121">1</span></span>     |<span data-ttu-id="f8fa9-122">5061</span><span class="sxs-lookup"><span data-stu-id="f8fa9-122">5061</span></span>     |<span data-ttu-id="f8fa9-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8fa9-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="f8fa9-124">У вас есть проверенный домен для Microsoft 365 или Office 365 (например, contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="f8fa9-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="f8fa9-125">Если в вашей организации не развернута система Microsoft 365 или Office 365, см. статью [Начало работы](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="f8fa9-126">Если в вашей организации не добавлен или не настроен проверенный домен для Microsoft 365 или Office 365, см. статью [Домены: вопросы и ответы](/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="f8fa9-127">В вашей организации развернуты решения Exchange Online и SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="f8fa9-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="f8fa9-128">Если в вашей организации нет Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](exchange-teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="f8fa9-129">Если в вашей организации нет SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="f8fa9-130">Убедившись, что эти требования к сетям выполнены, вы можете подготовиться к [развертыванию Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="f8fa9-131">Если ваша организация представляет собой крупную международную корпорацию, или заведомо существуют ограничения, связанные с сетями, прочтите оставшуюся часть этой статьи, чтобы узнать, как оценить состояние вашей сети и оптимизировать ее для Teams.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8fa9-132">**Для образовательных учреждений**: если ваша организация является образовательным учреждением, в котором используется система данных об учащихся (SIS), [разверните Синхронизацию сведений о школе](/schooldatasync/) перед развертыванием Teams.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="f8fa9-133">**Skype для бизнеса Server в локальной среде**: если в локальной среде вашей организации используется Skype для бизнеса Server (или Lync Server), необходимо [настроить Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) для синхронизации локального каталога с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="f8fa9-134">Рекомендация: мониторинг сети с использованием панели мониторинга качества звонка и аналитики звонков</span><span class="sxs-lookup"><span data-stu-id="f8fa9-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="f8fa9-135">Используйте [Панель мониторинга качества звонка (ПМКЗ)](turning-on-and-using-call-quality-dashboard.md), чтобы определить качество звонков и собраний в Teams.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="f8fa9-136">ПМКЗ помогает оптимизировать сеть, отслеживая ее качество, надежность и впечатления от ее использования.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="f8fa9-137">ПМКЗ рассматривает совокупную телеметрию для всей организации, где могут быть хорошо заметны общие шаблоны и тенденции. Это дает возможность выявлять проблемы и планировать меры по их устранению.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="f8fa9-138">Кроме того, ПМКЗ предоставляет отчеты с содержательными метриками, позволяющие оценить общее качество работы сети, ее надежность и впечатления от ее использования.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="f8fa9-139">Вы будете использовать [аналитику звонков](set-up-call-analytics.md) для изучения проблем со звонками и собраниями для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="f8fa9-140">Оптимизация сети</span><span class="sxs-lookup"><span data-stu-id="f8fa9-140">Network optimization</span></span>

<span data-ttu-id="f8fa9-141">Следующие задачи не являются обязательными и не требуются для развертывания Teams, особенно если ваша организация представляет собой компанию малого бизнеса, а вы уже развернули Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f8fa9-142">Воспользуйтесь этим руководством, чтобы оптимизировать производительность сети и Teams, а также в случае, если вам известно об ограничениях в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="f8fa9-143">Дополнительная оптимизация сети может потребоваться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f8fa9-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="f8fa9-144">Teams работает медленно (возможна недостаточная пропускная способность)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="f8fa9-145">Часто наблюдаются сбросы звонков (возможная причина: брандмауэр или блокировщики на прокси-сервере)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="f8fa9-146">Во время звонков слышен статический шум, возникают пропуски, голоса звучат механически (возможные причины: дрожание или потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="f8fa9-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="f8fa9-147">Подробное обсуждение оптимизации сети, включая рекомендации по выявлению и устранению сетевых нарушений, см. в статье[Принципы сетевых подключений в Microsoft 365 и Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f8fa9-148">Задача по оптимизации сети</span><span class="sxs-lookup"><span data-stu-id="f8fa9-148">Network optimization task</span></span></th>
<th><span data-ttu-id="f8fa9-149">Сведения</span><span class="sxs-lookup"><span data-stu-id="f8fa9-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f8fa9-150">Планировщик сети</span><span class="sxs-lookup"><span data-stu-id="f8fa9-150">Network planner</span></span></td>
<td><p><span data-ttu-id="f8fa9-151">Для помощи в оценки сети, включая расчет пропускной способности и требований к сетям в физических расположениях вашей организации, воспользуйтесь <a href="/microsoftteams/network-planner">планировщиком сети</a> в <a href="https://admin.teams.microsoft.com">Центре администрирования Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="f8fa9-152">Когда вы предоставляете сведения о сети и об использовании Teams, планировщик сети вычисляет требования к сети для развертывания Teams и облачных решений голосовой связи в физических расположениях вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="f8fa9-153">Пример сценария см. в статье <a href="/microsoftteams/tutorial-network-planner-example">Использование планировщика сети — пример сценария</a>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8fa9-154">Помощник для Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="f8fa9-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Помощник для Teams</a> — компонент <a href="https://admin.teams.microsoft.com">Центра администрирования Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="f8fa9-156">Он оценивает вашу среду Microsoft 365 или Office 365 и определяет самые распространенные конфигурации, которые может потребоваться обновить или изменить, чтобы успешно развернуть Teams.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8fa9-157">Внешнее разрешение имен</span><span class="sxs-lookup"><span data-stu-id="f8fa9-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="f8fa9-158">Все клиентские компьютеры, на которых установлен клиент Teams, должны быть способны разрешать внешние запросы DNS для обнаружения служб, предоставляемых системой Microsoft 365 или Office 365. Брандмауэры не должны запрещать доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="f8fa9-159">Сведения о настройке портов брандмауэра можно см. в статье <a href="/microsoftteams/office-365-urls-ip-address-ranges">URL-адреса и диапазоны IP-адресов Microsoft 365 и Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8fa9-160">Поддержание сохранения сеансов</span><span class="sxs-lookup"><span data-stu-id="f8fa9-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="f8fa9-161">Убедитесь, что ваш брандмауэр не изменяет сопоставленные адреса или порты преобразования сетевых адресов (NAT) для UDP.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="f8fa9-162">Проверка размера пула NAT</span><span class="sxs-lookup"><span data-stu-id="f8fa9-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="f8fa9-163">Проверьте размер пула преобразования сетевых адресов (NAT), необходимый для подключения пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="f8fa9-164">Когда множество пользователей или устройств обращаются к Microsoft 365 или Office 365 с использованием <a href="/office365/enterprise/nat-support-with-office-365">преобразования сетевых адресов (NAT) или преобразования адресов портов (PAT)</a>, нужно убедиться, что количество устройств, скрытых за каждым из общедоступных маршрутизируемых IP-адресов, не превышает поддерживаемое количество.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="f8fa9-165">Чтобы снизить риск нехватки портов, убедитесь, что пулам NAT назначено достаточное количество общедоступных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="f8fa9-166">При нехватке портов внутренние пользователи и устройства не смогут подключаться к службе Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8fa9-167">Маршрутизация в центры обработки данных Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f8fa9-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="f8fa9-168"><a href="/office365/enterprise/client-connectivity">Реализуйте наиболее эффективную маршрутизацию в центры обработки данных Майкрософт</a>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="f8fa9-169">Определите расположения, в которых можно использовать локальные или региональные точки выхода для наиболее эффективного подключения к сети Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8fa9-170">Указания по обнаружению и предотвращению вторжений</span><span class="sxs-lookup"><span data-stu-id="f8fa9-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="f8fa9-171">Если в вашей среде развернута система <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">обнаружения или предотвращения вторжений</a> (IDS/IPS) в качестве дополнительного уровня безопасности для исходящих подключений, не забудьте разрешить все URL-адреса Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8fa9-172">Настройка VPN с раздельным туннелированием</span><span class="sxs-lookup"><span data-stu-id="f8fa9-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="f8fa9-173">Мы рекомендуем предоставить для трафика Teams отдельный путь в обход виртуальной частной сети (VPN). Такая топология обычно называется <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN с раздельным туннелированием</a>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="f8fa9-174">Раздельное туннелирование означает, что трафик для Microsoft 365 или Office 365 проходит не через VPN, а идет напрямую в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f8fa9-175">Обход VPN положительно влияет на качество работы Teams и снимает нагрузку с VPN-устройств и сети организации.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="f8fa9-176">Чтобы реализовать раздельное туннелирование, обратитесь к поставщику VPN.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="f8fa9-177">Вот другие причины, по которым мы рекомендуем подключение в обход VPN:</span><span class="sxs-lookup"><span data-stu-id="f8fa9-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="f8fa9-178">Сети VPN обычно не предназначены или не настроены для поддержки мультимедиа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="f8fa9-179">Некоторые сети VPN также могут не поддерживать протокол UDP (он необходим для Teams).</span><span class="sxs-lookup"><span data-stu-id="f8fa9-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="f8fa9-180">Сети VPN также создают дополнительный уровень шифрования поверх уже зашифрованного трафика мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="f8fa9-181">Кроме того, возможность подключения к Teams может быть неэффективна из-за направления трафика через VPN-устройство.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8fa9-182">Реализация качества обслуживания</span><span class="sxs-lookup"><span data-stu-id="f8fa9-182">Implement QoS</span></span></td>
<td><span data-ttu-id="f8fa9-183"><a href="/microsoftteams/qos-in-teams">Используйте качество обслуживания (QoS)</a> для настройки приоритета пакетов.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="f8fa9-184">За счет этого повышается качество звонков в Teams, становится удобнее отслеживать качество звонков и устранять связанные с этим проблемы.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="f8fa9-185">Качество обслуживания должно быть реализовано во всех сегментах управляемой сети.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="f8fa9-186">Даже если для сети подготовлена достаточная пропускная способность, QoS снижает риск на случай непредвиденных сетевых событий.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="f8fa9-187">При реализации QoS приоритет имеет голосовой трафик, поэтому подобные непредвиденные события не будут иметь отрицательного влияния на качество.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8fa9-188">Оптимизация Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f8fa9-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="f8fa9-189">Как и VPN, сети Wi-Fi не всегда предназначены или настроены для поддержки мультимедиа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="f8fa9-190">Планирование и оптимизация сети Wi-Fi для поддержки Teams — важный фактор высококачественного развертывания.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="f8fa9-191">Учитывайте следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="f8fa9-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8fa9-192">Используйте QoS или Wi-Fi Multimedia (WMM) для обеспечения надлежащего приоритета трафика мультимедиа при передачи по сетям Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="f8fa9-193">Спланируйте и оптимизируйте диапазоны Wi-Fi и расположение точек доступа.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="f8fa9-194">Диапазон 2,4 ГГц способен обеспечить адекватное взаимодействие в зависимости от расположения точек доступа, но другие потребительские устройства, работающие в том же диапазоне, зачастую влияют на эти точки доступа.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="f8fa9-195">Диапазон 5 ГГц лучше подходит для мультимедиа в реальном времени за счет повышенной плотности, но в этом случае для достаточного охвата требуется больше точек доступа.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="f8fa9-196">Сами конечные точки должны поддерживать этот диапазон и должны быть настроены для его использования.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="f8fa9-197">При развертывании двухдиапазонных сетей Wi-Fi рекомендуется использовать функцию управления диапазонами.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="f8fa9-198"><em>Управление диапазонами</em> — это реализуемая поставщиками Wi-Fi функция, побуждающая двухдиапазонные клиенты использовать диапазон 5 ГГц.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="f8fa9-199">Когда точки доступа на одном канале расположены слишком близко друг к другу, это может вызвать перекрытие сигнала и непреднамеренную конкуренцию, что приведет к снижению удобства для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="f8fa9-200">Убедитесь, что расположенные рядом точки доступа используют каналы, которые не перекрывают друг друга.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="f8fa9-201">Каждый поставщик беспроводной связи предоставляет собственные рекомендации по развертыванию своих беспроводных решений.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="f8fa9-202">Обратитесь к своему поставщику Wi-Fi для получения конкретных рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="f8fa9-203">Требования к пропускной способности</span><span class="sxs-lookup"><span data-stu-id="f8fa9-203">Bandwidth requirements</span></span>

<span data-ttu-id="f8fa9-204">Приложение Teams устроено таким образом, чтобы обеспечивать наилучшие возможности предоставления доступа к звуку и видео и содержимому вне зависимости от состояния сети.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="f8fa9-205">Тем не менее, если пропускная способность недостаточна, качество звука в Teams будет иметь более высокий приоритет, чем качество видео.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="f8fa9-206">Если пропускная способность не имеет ограничений, Teams оптимизирует качество мультимедиа, включая высококачественный звук, разрешение видео до 1080p и со скоростью до 30 кадров/с для видео и содержимого.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="f8fa9-207">В этой таблице описано, как Teams использует пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="f8fa9-208">Отношение Teams к использованию пропускной способности остается неизменным и обеспечивает передачу видео высокой четкости при 1,5Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="f8fa9-209">Фактическое использование пропускной способности для каждого голосового или видеозвонка или собрания зависит от нескольких факторов, таких как макет видео, разрешение видео и количество кадров в секунду.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="f8fa9-210">Если доступна повышенная пропускная способность, качество и использование улучшатся для оптимального взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="f8fa9-211">**Модальность**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="f8fa9-212">**Требования к пропускной способности (битовая частота КБ/с вверх/вниз)**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f8fa9-213">**Минимальные**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f8fa9-214">**Рекомендуемые**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f8fa9-215">**Максимальная производительность**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8fa9-216">**Звук**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-217">Отношение "один-к-одному"</span><span class="sxs-lookup"><span data-stu-id="f8fa9-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-218">10/10</span><span class="sxs-lookup"><span data-stu-id="f8fa9-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-219">58/58</span><span class="sxs-lookup"><span data-stu-id="f8fa9-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-220">76/76</span><span class="sxs-lookup"><span data-stu-id="f8fa9-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-221">Собрания</span><span class="sxs-lookup"><span data-stu-id="f8fa9-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-222">10/10</span><span class="sxs-lookup"><span data-stu-id="f8fa9-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-223">58/58</span><span class="sxs-lookup"><span data-stu-id="f8fa9-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-224">76/76</span><span class="sxs-lookup"><span data-stu-id="f8fa9-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8fa9-225">**Видео**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-226">Отношение "один-к-одному"</span><span class="sxs-lookup"><span data-stu-id="f8fa9-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-227">150/150</span><span class="sxs-lookup"><span data-stu-id="f8fa9-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-228">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="f8fa9-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-229">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8fa9-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-230">Собрания</span><span class="sxs-lookup"><span data-stu-id="f8fa9-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-231">150/200</span><span class="sxs-lookup"><span data-stu-id="f8fa9-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-232">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="f8fa9-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-233">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8fa9-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8fa9-234">**Демонстрация экрана**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-235">Отношение "один-к-одному"</span><span class="sxs-lookup"><span data-stu-id="f8fa9-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-236">200/200</span><span class="sxs-lookup"><span data-stu-id="f8fa9-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-237">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="f8fa9-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-238">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8fa9-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-239">Собрания</span><span class="sxs-lookup"><span data-stu-id="f8fa9-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-240">250/250</span><span class="sxs-lookup"><span data-stu-id="f8fa9-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-241">2,500/2,500</span><span class="sxs-lookup"><span data-stu-id="f8fa9-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-242">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8fa9-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8fa9-243">**Режим "Вместе"**</span><span class="sxs-lookup"><span data-stu-id="f8fa9-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-244">Отношение "один-к-одному"</span><span class="sxs-lookup"><span data-stu-id="f8fa9-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-245">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f8fa9-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-246">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f8fa9-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-247">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f8fa9-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8fa9-248">Собрания</span><span class="sxs-lookup"><span data-stu-id="f8fa9-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-249">1,000/1,500</span><span class="sxs-lookup"><span data-stu-id="f8fa9-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-250">1,500/2,500</span><span class="sxs-lookup"><span data-stu-id="f8fa9-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8fa9-251">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="f8fa9-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="f8fa9-252">**Минимальные**, **Рекомендуемые** требования и требования **Максимальной производительности** к пропускной способности основаны на использовании конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="f8fa9-253">Как правило, для каждого пользователя существует одна конечная точка, например компьютер или мобильное устройство.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="f8fa9-254">Однако если пользователь присоединяется к собранию Teams *и на* компьютере, *и на* мобильном устройстве, с этим пользователем связываются две конечные точки.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="f8fa9-255">**Минимальные** требования пропускной способности для видеозвонков: разрешение до 240p, частота кадров для содержимого демонстрации экрана — от 1,875 до 7,5 кадров/с, а разрешение видео в режиме "Вместе" или "Большая галерея" — до 540p.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="f8fa9-256">**Рекомендуемые** требования пропускной способности для видеозвонков: разрешение до 1080p<sup>\*</sup>, частота кадров для содержимого демонстрации экрана — от 7,5 до 30 кадров/с, а разрешение видео в режиме "Вместе" или "Большая галерея" — до 1080p<sup>\*</sup>.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="f8fa9-257">Инструкции по **максимальной производительности** обеспечивают более точное воспроизведение видео для собраний с большим количеством участников, сред с высокими потерями и контента с более высоким уровнем движения с частотой кадров контента демонстрации экрана от 15 до 30 кадров/с.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="f8fa9-258"><sup>\*</sup>Ожидайте качество до 1080p, но в зависимости от условий вашей сети разрешение и качество видео будут соответственно оптимизированы.</span><span class="sxs-lookup"><span data-stu-id="f8fa9-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="f8fa9-259">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f8fa9-259">Related Topics</span></span>

[<span data-ttu-id="f8fa9-260">Принципы сетевых подключений в Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="f8fa9-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="f8fa9-261">Конечные точки во всем мире: Skype для бизнеса Online и Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="f8fa9-262">Прокси-серверы для Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="f8fa9-263">Мультимедиа в Teams: почему собрания простые</span><span class="sxs-lookup"><span data-stu-id="f8fa9-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="f8fa9-264">Мультимедиа в Teams: погружение в потоки мультимедиа</span><span class="sxs-lookup"><span data-stu-id="f8fa9-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="f8fa9-265">Модели удостоверений и проверка подлинности в Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="f8fa9-266">Как выполнить развертывание Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="f8fa9-267">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="f8fa9-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
