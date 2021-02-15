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
description: Узнайте о функции трансляции собраний Skype в Skype для бизнеса Online, которая позволяет планировать, создавать и транслировать собрания или события крупной онлайн-аудитории до 10 000 участников.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865163"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="b7040-103">Настройка сети для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="b7040-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="b7040-104">После того [как вы введете](enable-skype-meeting-broadcast.md) трансляцию собрания Skype, необходимо настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="b7040-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="b7040-105">Сделайте это, если вы хотите проводить вебинары и другие трансляции для людей не из вашей компании.</span><span class="sxs-lookup"><span data-stu-id="b7040-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7040-106">Skype для бизнеса Online больше не будет работать 31 июля 2021 г., после чего доступ к службе закончится.</span><span class="sxs-lookup"><span data-stu-id="b7040-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="b7040-107">Мы рекомендуем клиентам начать обновление до Microsoft Teams, основного клиента для связи и командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7040-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="b7040-108">Если у вас нет опыта в настройке брандмауэра, вы можете нанять партнера Майкрософт, который сделает это за вас. [](https://go.microsoft.com/fwlink/?linkid=391089)</span><span class="sxs-lookup"><span data-stu-id="b7040-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="b7040-109">Чтобы пропустить этот шаг и добавить в вашу федерацию еще одну компания, чтобы пригласить их в трансляцию, выполните действия, которые необходимо предпринять, чтобы разрешить пользователям связываться с внешними пользователями [Skype для бизнеса.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="b7040-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="b7040-110">Шаг 1. Настройка разрешенных доменов</span><span class="sxs-lookup"><span data-stu-id="b7040-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="b7040-111">Чтобы **настроить разрешенные** домены, воспользуйтесь одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b7040-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="b7040-112">**Способ 1. Использование Центра администрирования**</span><span class="sxs-lookup"><span data-stu-id="b7040-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="b7040-113">Перейдите в Центр администрирования, а затем в области слева щелкните надстройки **"Службы** параметров" и выберите Skype  >  **&amp;** **для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="b7040-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="b7040-114">На странице **внешнего общего** доступа в разделе **Domain exceptions**(Исключения домена) выберите все домены, кроме и введите следующие домены через запятую (,):</span><span class="sxs-lookup"><span data-stu-id="b7040-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="b7040-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7040-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="b7040-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7040-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="b7040-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7040-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="b7040-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7040-118">resources.lync.com</span></span>

3. <span data-ttu-id="b7040-119">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b7040-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="b7040-120">**Способ 2. Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b7040-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="b7040-121">В меню **"Пуск"** щелкните правой кнопкой **мыши** Windows PowerShell выберите "Запуск **от администратора".**</span><span class="sxs-lookup"><span data-stu-id="b7040-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="b7040-122">В **Windows PowerShell** введите каждую строку и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="b7040-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="b7040-123">Шаг 2. Добавление доменов, URL-адресов и IP-адресов для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="b7040-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="b7040-124">Вторым этапом настройки является добавление необходимых доменов, а затем добавление IP-адресов и URL-адресов, необходимых для работы трансляции собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="b7040-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="b7040-125">**Добавьте необходимые URL-адреса** и IP-адреса конечных точек Skype для бизнеса Online, чтобы увидеть, какие из них здесь [необходимы.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)</span><span class="sxs-lookup"><span data-stu-id="b7040-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="b7040-126">Настройка трансляции собраний Skype в гибридных развертываниях и организациях</span><span class="sxs-lookup"><span data-stu-id="b7040-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="b7040-127">Если у вас есть организация Skype для бизнеса Online и локальное развертывание Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015, а пользователи находятся как в сети, так и локально, вам потребуется настроить ее, помимо перечисленных выше, чтобы разрешить локальной организации общаться со Skype для бизнеса Online и разрешить всем пользователям присоединяться к трансляции собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="b7040-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="b7040-128">Чтобы узнать, какие это требования, см. в настройках локального развертывания для [трансляции собраний Skype.](https://go.microsoft.com/fwlink/?LinkId=617070)</span><span class="sxs-lookup"><span data-stu-id="b7040-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7040-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b7040-129">Related topics</span></span>

[<span data-ttu-id="b7040-130">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="b7040-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="b7040-131">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="b7040-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="b7040-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b7040-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



