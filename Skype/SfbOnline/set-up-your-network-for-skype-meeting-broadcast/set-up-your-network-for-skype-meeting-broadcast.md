---
title: Настройка сети для вещания Скайп собрания
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Сведения о функцию вещания собрания Скайп Скайп для бизнеса в Интернет, который позволяет расписания, создавать и вещания собрания или события для крупных online аудиторий до 10 000 участников.
ms.openlocfilehash: 62c1f1fea7042230210d123c6d7fb88ff839d6f4
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="b41b1-103">Настройка сети для вещания Скайп собрания</span><span class="sxs-lookup"><span data-stu-id="b41b1-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="b41b1-104">После можно [Включить вещания собрания Скайп](enable-skype-meeting-broadcast.md) Скайп вещания собрания вам нужно настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="b41b1-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="b41b1-105">Выполните этот шаг, если требуется хранение семинары и другие вещании по пользователям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b41b1-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="b41b1-106">Если у вас нет опыта в настройке брандмауэра, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).</span><span class="sxs-lookup"><span data-stu-id="b41b1-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="b41b1-107">Чтобы пропустить этот этап и вместо этого добавьте другой компании, чтобы их можно пригласить вещании вашей федерации, следуйте указаниям в [Разрешить пользователям включать поддержку для связи внешних Скайп для коммерческих пользователей](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="b41b1-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="b41b1-108">Этап 1: Настройка разрешенных доменов</span><span class="sxs-lookup"><span data-stu-id="b41b1-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="b41b1-109">Используйте **один** из следующих методов для настройки разрешенных доменов:</span><span class="sxs-lookup"><span data-stu-id="b41b1-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="b41b1-110">**Способ 1: С помощью центра администрирования Office 365**</span><span class="sxs-lookup"><span data-stu-id="b41b1-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="b41b1-111">Перейдите в **Центр администрирования Office 365** и выберите **Параметры**в левая навигационная панель > **служб &amp; надстройки**, а затем нажмите **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b41b1-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="b41b1-112">На странице " **внешний общий доступ** " в разделе **исключения домена**выберите **все домены, блокируются за исключением**и введите следующие доменов, разделенных точкой с запятой (,):</span><span class="sxs-lookup"><span data-stu-id="b41b1-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="b41b1-113">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="b41b1-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="b41b1-114">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="b41b1-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="b41b1-115">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="b41b1-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="b41b1-116">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="b41b1-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="b41b1-117">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="b41b1-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="b41b1-118">**Способ 2: С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b41b1-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="b41b1-119">В **Меню "Пуск"**щелкните правой кнопкой мыши **Windows PowerShell** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="b41b1-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="b41b1-120">В окне **Windows PowerShell** введите каждую строку и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b41b1-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="b41b1-121">Шаг 2: Добавление доменов вещания Скайп собрания, URL-адреса и IP-адресов</span><span class="sxs-lookup"><span data-stu-id="b41b1-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="b41b1-122">— Это второй шаг в процессе установки необходимо сначала добавить доменов, которые необходимы, а затем добавьте IP-адресов и URL-адреса, которые необходимы для Скайп собрания вещания для работы.</span><span class="sxs-lookup"><span data-stu-id="b41b1-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="b41b1-123">**Добавьте необходимые Скайп для бизнеса в Интернет URL-адреса конечной точки и IP-адресов, достаточно какие из них являются обязательными** [здесь](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="b41b1-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="b41b1-124">Настройка широковещательного Скайп собрания в гибридных развертываниях и организаций</span><span class="sxs-lookup"><span data-stu-id="b41b1-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="b41b1-125">Если вы Скайп для бизнеса сети организации и локального развертывания Lync Server 2010, Microsoft Lync Server 2013 и Скайп для Business Server 2015 и имеют пользователей обоих Интернет-версия и локальной, но и других действий, которые необходимо выполнить дополнение к пример выше для включения в локальной организации для взаимодействия с Скайп для бизнеса в Интернет и разрешить всем пользователям возможность создавать и присоединиться к собранию Скайп, вещания.</span><span class="sxs-lookup"><span data-stu-id="b41b1-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="b41b1-126">Чтобы узнать, что этих требований, содержатся в разделе [Настройка локального развертывания на наличие Скайп собрания вещания](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="b41b1-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b41b1-127">See also</span><span class="sxs-lookup"><span data-stu-id="b41b1-127">Related topics</span></span>

[<span data-ttu-id="b41b1-128">Включение трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="b41b1-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="b41b1-129">URL-адреса и диапазоны IP-адресов Office 365</span><span class="sxs-lookup"><span data-stu-id="b41b1-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="b41b1-130">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b41b1-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
  
 
