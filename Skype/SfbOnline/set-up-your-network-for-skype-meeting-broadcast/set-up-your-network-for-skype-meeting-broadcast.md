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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Узнайте о функции Skype трансляции собраний в Skype для бизнеса Online, которая позволяет планировать, создавать и транслировать собрания или события крупной онлайн-аудитории до 10 000 участников.
ms.openlocfilehash: da27110313765bb50df92e3bafb6f09ceae5f301
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237555"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="dd913-103">Настройка сети для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="dd913-103">Set up your network for Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="dd913-104">После того [как Skype трансляцию](enable-skype-meeting-broadcast.md) Skype собрания, необходимо настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="dd913-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="dd913-105">Сделайте это, если вы хотите проводить вебинары и другие трансляции для людей за пределами вашей компании.</span><span class="sxs-lookup"><span data-stu-id="dd913-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd913-106">Skype для бизнеса 31 июля 2021 г. заканчивается доступ к службе Online.</span><span class="sxs-lookup"><span data-stu-id="dd913-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="dd913-107">Мы рекомендуем клиентам начать обновление до Microsoft Teams , основного клиента для связи и командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd913-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="dd913-108">Если у вас нет опыта настройки брандмауэра, [](https://go.microsoft.com/fwlink/?linkid=391089) вы можете нанять партнера Майкрософт, который сделает это за вас.</span><span class="sxs-lookup"><span data-stu-id="dd913-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="dd913-109">Чтобы пропустить этот шаг и вместо этого добавить в свою федерацию еще одну компания, чтобы пригласить их в трансляцию, выполните действия, которые можно сделать в области Разрешить пользователям связываться с внешними Skype для бизнеса [пользователями.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="dd913-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="dd913-110">Шаг 1. Настройка разрешенных доменов</span><span class="sxs-lookup"><span data-stu-id="dd913-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="dd913-111">Чтобы **настроить разрешенные** домены, используйте один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="dd913-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="dd913-112">**Способ 1. Использование Центра администрирования**</span><span class="sxs-lookup"><span data-stu-id="dd913-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="dd913-113">Перейдите в Центр администрирования, а затем в области слева щелкните надстройки **Параметры**  >  **&amp; services** и выберите Skype для бизнеса .</span><span class="sxs-lookup"><span data-stu-id="dd913-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="dd913-114">На странице **Внешнее общий** доступ в разделе Исключения домена **выберите** Все домены заблокированы, кроме и введите следующие домены, разделяя их запятой (,):</span><span class="sxs-lookup"><span data-stu-id="dd913-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="dd913-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dd913-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="dd913-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dd913-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="dd913-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dd913-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="dd913-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="dd913-118">resources.lync.com</span></span>

3. <span data-ttu-id="dd913-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dd913-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="dd913-120">**Способ 2. Используйте Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dd913-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="dd913-121">В меню **"Пуск"** щелкните правой **кнопкой** мыши Windows PowerShell выберите пункт **Запуск от администратора**.</span><span class="sxs-lookup"><span data-stu-id="dd913-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="dd913-122">В **окне** Windows PowerShell введите каждую строку и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="dd913-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="dd913-123">Шаг 2. Добавление Skype доменов, URL-адресов и IP-адресов Skype трансляции собраний</span><span class="sxs-lookup"><span data-stu-id="dd913-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="dd913-124">Второй этап настройки — добавление необходимых доменов, а затем добавление IP-адресов и URL-адресов, необходимых для Skype трансляции собраний.</span><span class="sxs-lookup"><span data-stu-id="dd913-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="dd913-125">**Добавьте необходимые URL Skype для бизнеса и IP-адреса** конечных точек Online, чтобы увидеть, какие из них здесь [необходимы.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)</span><span class="sxs-lookup"><span data-stu-id="dd913-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="dd913-126">Настройка трансляции Skype собраний в гибридных развертываниях и организациях</span><span class="sxs-lookup"><span data-stu-id="dd913-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="dd913-127">Если у вас есть организация Skype для бизнеса Online и локальное развертывание Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015, а также есть пользователи как в сети, так и локально, вам потребуется настроить дополнительные действия, помимо перечисленных выше, чтобы разрешить вашей локальной организации общаться с Skype для бизнеса Online и разрешить всем пользователям присоединиться к трансляции собрания Skype.</span><span class="sxs-lookup"><span data-stu-id="dd913-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="dd913-128">Чтобы узнать, каковы эти требования, см. настройка локального развертывания для [Skype трансляции собраний.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="dd913-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd913-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dd913-129">Related topics</span></span>

[<span data-ttu-id="dd913-130">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="dd913-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="dd913-131">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="dd913-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="dd913-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dd913-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
