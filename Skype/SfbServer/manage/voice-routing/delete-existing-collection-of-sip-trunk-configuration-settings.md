---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг. '
ms.openlocfilehash: 6a7c90bf7ff435b0936b34bc57d391e06093040a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879366"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="431bc-103">Удаление существующей коллекции параметров конфигурации магистрали SIP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="431bc-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="431bc-104">Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="431bc-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="431bc-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="431bc-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="431bc-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="431bc-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="431bc-107">Условия, при которых отправляются пакеты протокола RTCP управления транспорта реального времени.</span><span class="sxs-lookup"><span data-stu-id="431bc-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="431bc-108">На каждой линии связи требуется ли шифрование по протоколу (SRTP).</span><span class="sxs-lookup"><span data-stu-id="431bc-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="431bc-109">При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="431bc-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="431bc-110">Не удается удалить этот глобальной коллекции параметров.</span><span class="sxs-lookup"><span data-stu-id="431bc-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="431bc-111">Тем не менее можно использовать Скайп для бизнеса ServerControl панель или командлет [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) «очистить» свойства в глобальную коллекцию значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="431bc-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="431bc-112">Например если задано свойство Enable3pccRefer имеет значение True, то при сбросе глобальную коллекцию свойство Enable3pccRefer восстановит в значение по умолчанию False.</span><span class="sxs-lookup"><span data-stu-id="431bc-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="431bc-113">Администраторы могут также создавать настраиваемые магистрали параметров конфигурации на уровне сайта или на уровне службы (для отдельных шлюза ТСОП); Эти параметры можно удалить.</span><span class="sxs-lookup"><span data-stu-id="431bc-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="431bc-114">При удалении этих настраиваемых параметров помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="431bc-114">When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="431bc-115">Если удалить параметры области действия службы, затем магистраль SIP, управляемые этими параметрами управляемые параметры, примененные к их сайта, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="431bc-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="431bc-116">Если параметры сайта не существует, эти магистралях затем будут управляться глобальной коллекции параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="431bc-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="431bc-117">Если удалить параметры области сайта выберите любые магистральные линии SIP, управляемые этими параметрами будут управляться глобальной коллекции параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="431bc-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="431bc-118">**Удаление параметров конфигурации магистрали с Скайп для панели управления Business Server**</span><span class="sxs-lookup"><span data-stu-id="431bc-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="431bc-119">В Скайп для панели управления Business Server щелкните **Маршрутизация голосовой связи**и затем щелкните **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="431bc-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="431bc-120">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистрали SIP, чтобы удалить, нажмите кнопку **Изменить**и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="431bc-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="431bc-121">Для удаления нескольких семейств сайтов в той же операции, нажмите кнопку первой коллекции, которую требуется удалить, а затем удерживайте нажатой клавишу Ctrl и щелкните любые дополнительные коллекции, которые вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="431bc-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="431bc-p106">Свойство **Состояние** для коллекции будет обновлено до **Не сохранено**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="431bc-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="431bc-124">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="431bc-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="431bc-125">В диалоговом окне **Скайп для панели управления Business Server** нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="431bc-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="431bc-126">Если решено не удалять семейство сайтов, нажмите кнопку **зафиксировать**и нажмите кнопку **Отмена всех незафиксированных изменений**окно.</span><span class="sxs-lookup"><span data-stu-id="431bc-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="431bc-127">Когда появится диалоговое окно **Скайп для панели управления Business Server** , нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="431bc-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="431bc-128">Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="431bc-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="431bc-129">Параметры конфигурации можно удалить с помощью Windows PowerShell и командлет **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="431bc-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="431bc-130">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="431bc-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="431bc-131">**Удаление указанной коллекции параметров**</span><span class="sxs-lookup"><span data-stu-id="431bc-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="431bc-132">Следующая команда удаляет параметры конфигурации, применяемые к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="431bc-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="431bc-133">**Удаление всех коллекций, примененных на уровне сайта**</span><span class="sxs-lookup"><span data-stu-id="431bc-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="431bc-134">Эта команда удаляет все параметры конфигурации магистральной линии связи, применяемых на уровне службы:</span><span class="sxs-lookup"><span data-stu-id="431bc-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="431bc-135">**Чтобы удалить все семейства сайтов, где сервера-посредника включена**</span><span class="sxs-lookup"><span data-stu-id="431bc-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="431bc-136">Следующая команда удаляет все параметры конфигурации, где сервера-посредника был включен.</span><span class="sxs-lookup"><span data-stu-id="431bc-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="431bc-137">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="431bc-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
