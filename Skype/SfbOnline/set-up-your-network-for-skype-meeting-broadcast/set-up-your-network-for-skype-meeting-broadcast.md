---
title: Настройка сети для трансляции собраний Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Узнайте о функциях трансляции собраний Skype в Skype для бизнеса Online, которая позволяет планировать, создавать и транслировать собрания или события для больших Интернет-пользователей до 10 000 участников.
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990984"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="c9a1c-103">Настройка сети для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="c9a1c-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="c9a1c-104">После [включения](enable-skype-meeting-broadcast.md) трансляции собраний Skype в Skype необходимо настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="c9a1c-105">Если вы хотите хранить семинары и другие трансляции для пользователей за пределами вашей организации, выполните это действие.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="c9a1c-106">Если вы не сталкивались с настройкой межсетевого экрана, рассматривайте для этого действия [партнера Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) .</span><span class="sxs-lookup"><span data-stu-id="c9a1c-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="c9a1c-107">Чтобы пропустить этот шаг и добавить еще один бизнес в Федерацию, чтобы вы могли пригласить их на широковещательные показы, выполните действия, описанные в статье [Разрешение пользователей для связи с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="c9a1c-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="c9a1c-108">Шаг 1: Настройка разрешенных доменов</span><span class="sxs-lookup"><span data-stu-id="c9a1c-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="c9a1c-109">Чтобы настроить разрешенные домены, воспользуйтесь **одним** из описанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="c9a1c-110">**Способ 1: использование центра администрирования**</span><span class="sxs-lookup"><span data-stu-id="c9a1c-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="c9a1c-111">Перейдите в центр администрирования, а затем на панели навигации слева щелкните надстройки\*\*службы &amp; \*\* **параметров** > и выберите **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="c9a1c-112">На странице **внешний общий доступ** в разделе **исключения домена**, выберите **все домены заблокированы, Кроме того**, введите указанные ниже домены, разделяя их запятыми (,).</span><span class="sxs-lookup"><span data-stu-id="c9a1c-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="c9a1c-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9a1c-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="c9a1c-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9a1c-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="c9a1c-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9a1c-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="c9a1c-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="c9a1c-116">resources.lync.com</span></span>

3. <span data-ttu-id="c9a1c-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="c9a1c-118">**Способ 2: использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c9a1c-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="c9a1c-119">В **меню "Пуск**" щелкните правой кнопкой мыши **Windows PowerShell** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="c9a1c-120">В окне **Windows PowerShell** введите каждую строку и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="c9a1c-121">Шаг 2: Добавьте домены трансляции собраний Skype, URL-адреса и адреса IP.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="c9a1c-122">На втором этапе процесса настройки нужно добавить необходимые домены, а затем добавить IP-адреса и URL-адреса, необходимые для работы трансляции собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="c9a1c-123">**Добавьте нужные URL-адреса конечных точек Skype для бизнеса Online и IP-адреса, чтобы увидеть, какие из них вам нужны** [.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)</span><span class="sxs-lookup"><span data-stu-id="c9a1c-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="c9a1c-124">Настройка трансляции собраний Skype в гибридных развертываниях и организациях</span><span class="sxs-lookup"><span data-stu-id="c9a1c-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="c9a1c-125">Если у вас есть организация Skype для бизнеса Online и локальное развертывание Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015 и у них есть другие пользователи в сети и локально, необходимо выполнить другие действия по настройке, описанные в этой статье. Помимо описанных выше, чтобы предоставить локальной организации возможность общения с Skype для бизнеса Online и разрешить всем пользователям присоединиться к трансляции собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="c9a1c-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="c9a1c-126">Чтобы узнать о требованиях, ознакомьтесь с разрешениями [Настройка локального развертывания для трансляции собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="c9a1c-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9a1c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c9a1c-127">Related topics</span></span>

[<span data-ttu-id="c9a1c-128">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="c9a1c-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="c9a1c-129">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="c9a1c-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="c9a1c-130">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c9a1c-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



