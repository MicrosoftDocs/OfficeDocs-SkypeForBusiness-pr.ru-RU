---
title: Удаление существующей коллекции параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274935"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e8930-103">Удаление существующей коллекции параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8930-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="e8930-104">Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="e8930-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="e8930-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="e8930-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="e8930-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="e8930-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="e8930-107">Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="e8930-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="e8930-108">Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).</span><span class="sxs-lookup"><span data-stu-id="e8930-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e8930-109">При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="e8930-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e8930-110">Этот глобальный набор параметров нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="e8930-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="e8930-111">Тем не менее, вы можете использовать Серверконтрол панель Skype для бизнеса или командлет [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) для восстановления значений по умолчанию для свойств в глобальной коллекции.</span><span class="sxs-lookup"><span data-stu-id="e8930-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="e8930-112">Например, если для свойства Enable3pccRefer задано значение "true", при сбросе глобальной коллекции к значению по умолчанию для свойства Enable3pccRefer будет возвращено значение false.</span><span class="sxs-lookup"><span data-stu-id="e8930-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="e8930-113">Кроме того, администраторы могут создавать пользовательские параметры для настройки магистрали в области сайта или в области обслуживания (для отдельного шлюза PSTN); Эти пользовательские параметры можно удалить.</span><span class="sxs-lookup"><span data-stu-id="e8930-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="e8930-114">При удалении этих настраиваемых параметров следует учитывать указанные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="e8930-114">When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="e8930-115">Если вы удалите параметры области службы, то магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к своему сайту (если они существуют).</span><span class="sxs-lookup"><span data-stu-id="e8930-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="e8930-116">Если параметр "Параметры сайта" не существует, эти магистрали будут управляться глобальной коллекцией параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="e8930-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="e8930-117">После удаления параметров уровня сайта все магистральные элементы SIP, управляемые этими параметрами, теперь будут управляться глобальной коллекцией параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="e8930-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="e8930-118">**Удаление параметров конфигурации канала с помощью панели управления "Skype для бизнеса" на сервере**</span><span class="sxs-lookup"><span data-stu-id="e8930-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="e8930-119">На панели управления Skype для бизнеса Server нажмите кнопку **Маршрутизация голоса**и выберите пункт **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="e8930-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="e8930-120">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистральной магистрали, которые нужно удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e8930-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="e8930-121">Чтобы удалить несколько коллекций в одной операции, щелкните первую из них, которую нужно удалить, а затем, удерживая нажатой клавишу CTRL, щелкните все дополнительные коллекции, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="e8930-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="e8930-p106">Свойство **Состояние** для коллекции будет обновлено до **Не сохранено**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="e8930-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="e8930-124">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8930-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="e8930-125">В диалоговом окне **Панель управления "Skype для бизнеса Server** " нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8930-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="e8930-126">Если вы передумали и решили не удалять коллекцию, нажмите кнопку **сохранить**, а затем — **отменить все незафиксированные изменения**.</span><span class="sxs-lookup"><span data-stu-id="e8930-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="e8930-127">Когда появится диалоговое окно " **Панель управления" в Skype для бизнеса Server** , нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8930-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8930-128">Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8930-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="e8930-129">Вы можете удалить параметры конфигурации канала с помощью Windows PowerShell и командлета **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e8930-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="e8930-130">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8930-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="e8930-131">**Удаление заданной коллекции параметров**</span><span class="sxs-lookup"><span data-stu-id="e8930-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="e8930-132">Следующая команда удаляет параметры конфигурации магистрали, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="e8930-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="e8930-133">**Удаление всех коллекций, примененных к области сайта**</span><span class="sxs-lookup"><span data-stu-id="e8930-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="e8930-134">Эта команда удаляет все параметры конфигурации канала, примененные к области обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e8930-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="e8930-135">**Удаление всех коллекций с включенным обходом мультимедиа**</span><span class="sxs-lookup"><span data-stu-id="e8930-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="e8930-136">Следующая команда удаляет все параметры конфигурации канала, в которых включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e8930-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="e8930-137">Дополнительные сведения можно найти в разделе справки по командлету [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e8930-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
