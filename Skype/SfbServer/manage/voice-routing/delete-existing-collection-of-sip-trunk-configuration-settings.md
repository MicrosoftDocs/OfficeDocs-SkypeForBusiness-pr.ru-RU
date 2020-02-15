---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг. '
ms.openlocfilehash: 09f5e7fda03c5e0e5221661f87482b67192ce302
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045061"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="97a0c-103">Удаление существующей коллекции параметров конфигурации магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="97a0c-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="97a0c-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="97a0c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="97a0c-106">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="97a0c-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="97a0c-107">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="97a0c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="97a0c-108">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="97a0c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="97a0c-109">При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="97a0c-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="97a0c-110">Эта глобальная коллекция параметров не подлежит удалению.</span><span class="sxs-lookup"><span data-stu-id="97a0c-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="97a0c-111">Тем не менее, с помощью Серверконтрол панели Skype для бизнеса или командлета [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) можно сбросить свойства в глобальной коллекции на значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="97a0c-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="97a0c-112">Например, если задать свойство Enable3pccRefer как True, то при сбросе глобальной коллекции для свойства Enable3pccRefer возвращается значение по умолчанию False.</span><span class="sxs-lookup"><span data-stu-id="97a0c-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="97a0c-p103">Администраторы могут также создавать пользовательские параметры конфигурации магистральной линии для области сайта или службы (отдельного шлюза ТСОП); эти пользовательские параметры могут быть удалены. При удалении данных пользовательских параметров следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="97a0c-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="97a0c-p104">Если удалить параметры области службы, магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к их сайту, если эти параметры существуют. Если параметры сайта не существуют, эти магистральные линии будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="97a0c-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="97a0c-117">Если удалить параметры области сайта, любые магистральные линии SIP, управляемые этими параметрами, будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="97a0c-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="97a0c-118">**Удаление параметров конфигурации магистрали с помощью панели управления Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="97a0c-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="97a0c-119">На панели управления Skype для бизнеса Server щелкните **Маршрутизация голосовой связи**, а затем щелкните **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="97a0c-120">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистральной линии SIP, которую необходимо удалить, нажмите кнопку **изменить**, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="97a0c-121">Чтобы удалить несколько коллекций одновременно, щелкните первую удаляемую коллекцию, затем, удерживая нажатой клавишу Ctrl, щелкайте любые другие коллекции, которые следует удалить.</span><span class="sxs-lookup"><span data-stu-id="97a0c-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="97a0c-p106">Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="97a0c-124">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="97a0c-125">В диалоговом окне " **Панель управления Skype для бизнеса Server** " нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="97a0c-126">Если вы передумали и решили не удалять коллекцию, нажмите кнопку **зафиксировать**, а затем — **Отмена всех незафиксированных изменений**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="97a0c-127">Когда появится диалоговое окно " **Панель управления Skype для бизнеса Server** ", нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="97a0c-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="97a0c-128">Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="97a0c-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="97a0c-129">Параметры конфигурации магистрали можно удалить с помощью Windows PowerShell и командлета **Remove – CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="97a0c-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="97a0c-130">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97a0c-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="97a0c-131">**Удаление заданной коллекции параметров**</span><span class="sxs-lookup"><span data-stu-id="97a0c-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="97a0c-132">Следующая команда удаляет параметры конфигурации магистральной линии в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="97a0c-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="97a0c-133">**Удаление всех коллекций, примененных к области сайта**</span><span class="sxs-lookup"><span data-stu-id="97a0c-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="97a0c-134">Эта команда удаляет все параметры конфигурации магистральной линии, примененные на уровне службы:</span><span class="sxs-lookup"><span data-stu-id="97a0c-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="97a0c-135">**Удаление всех коллекций, где включен обход сервера-посредника**</span><span class="sxs-lookup"><span data-stu-id="97a0c-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="97a0c-136">Следующая команда удаляет все параметры конфигурации, где был включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="97a0c-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="97a0c-137">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="97a0c-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
