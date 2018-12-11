---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг. '
ms.openlocfilehash: 3d568e07dd4baec59f050453087b2857a72377d4
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223481"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="5c286-103">Удаление существующей коллекции параметров конфигурации магистрали SIP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5c286-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="5c286-104">Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="5c286-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="5c286-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="5c286-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="5c286-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="5c286-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="5c286-107">Условия, при которых отправляются пакеты протокола RTCP управления транспорта реального времени.</span><span class="sxs-lookup"><span data-stu-id="5c286-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="5c286-108">На каждой линии связи требуется ли шифрование по протоколу (SRTP).</span><span class="sxs-lookup"><span data-stu-id="5c286-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="5c286-109">При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="5c286-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="5c286-110">This global collection of settings cannot be deleted.</span><span class="sxs-lookup"><span data-stu-id="5c286-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="5c286-111">Тем не менее можно использовать Скайп для бизнеса ServerControl панель или командлет [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) «очистить» свойства в глобальную коллекцию значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c286-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="5c286-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span><span class="sxs-lookup"><span data-stu-id="5c286-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="5c286-p103">Администраторы могут также создавать пользовательские параметры конфигурации магистральной линии для области сайта или службы (отдельного шлюза ТСОП); эти пользовательские параметры могут быть удалены. При удалении данных пользовательских параметров следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="5c286-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="5c286-p104">Если удалить параметры области службы, магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к их сайту, если эти параметры существуют. Если параметры сайта не существуют, эти магистральные линии будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="5c286-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="5c286-117">Если удалить параметры области сайта, любые магистральные линии SIP, управляемые этими параметрами, будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="5c286-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="5c286-118">**Удаление параметров конфигурации магистрали с Скайп для панели управления Business Server**</span><span class="sxs-lookup"><span data-stu-id="5c286-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="5c286-119">В Скайп для панели управления Business Server щелкните **Маршрутизация голосовой связи**и затем щелкните **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="5c286-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="5c286-120">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистрали SIP, чтобы удалить, нажмите кнопку **Изменить**и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="5c286-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="5c286-121">Чтобы удалить несколько коллекций одновременно, щелкните первую удаляемую коллекцию, затем, удерживая нажатой клавишу Ctrl, щелкайте любые другие коллекции, которые следует удалить.</span><span class="sxs-lookup"><span data-stu-id="5c286-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="5c286-p106">Свойство **Состояние** для коллекции будет обновлено до **Не сохранено**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="5c286-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="5c286-124">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5c286-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="5c286-125">В диалоговом окне **Скайп для панели управления Business Server** нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="5c286-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="5c286-126">Если решено не удалять семейство сайтов, нажмите кнопку **зафиксировать**и нажмите кнопку **Отмена всех незафиксированных изменений**окно.</span><span class="sxs-lookup"><span data-stu-id="5c286-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="5c286-127">Когда появится диалоговое окно **Скайп для панели управления Business Server** , нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="5c286-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5c286-128">Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c286-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="5c286-129">Параметры конфигурации можно удалить с помощью Windows PowerShell и командлет **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5c286-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="5c286-130">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c286-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="5c286-131">**Удаление указанной коллекции параметров**</span><span class="sxs-lookup"><span data-stu-id="5c286-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="5c286-132">Следующая команда удаляет параметры конфигурации магистральной линии в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="5c286-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="5c286-133">**Удаление всех коллекций, применяемых на уровне сайта**</span><span class="sxs-lookup"><span data-stu-id="5c286-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="5c286-134">Эта команда удаляет все параметры конфигурации магистральной линии, примененные на уровне службы:</span><span class="sxs-lookup"><span data-stu-id="5c286-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="5c286-135">**Удаление всех коллекций, где включен обход сервера-посредника**</span><span class="sxs-lookup"><span data-stu-id="5c286-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="5c286-136">Следующая команда удаляет все параметры конфигурации, где был включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5c286-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="5c286-137">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5c286-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>