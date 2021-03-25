---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: Сводка. Узнайте, как удалить коллекцию параметров конфигурации магистрали с помощью панели управления Skype для бизнес-серверов.
ms.openlocfilehash: 8ea3ef931c8e09a235adc816cd993468d7d79b47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111855"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="417b6-103">Удаление существующей коллекции параметров конфигурации магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="417b6-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="417b6-104">**Сводка:** Узнайте, как удалить коллекцию параметров конфигурации магистрали с помощью панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="417b6-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="417b6-105">Параметры конфигурации магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом открытой телефонной сети (PSTN), шлюзом IP-Public Branch eXchange (PBX) или диспетчером пограничной связи сеанса (SBC) у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="417b6-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="417b6-106">Эти настройки можно использовать, чтобы определить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="417b6-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="417b6-107">Следует ли включать обход сервера-посредника на магистралях.</span><span class="sxs-lookup"><span data-stu-id="417b6-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="417b6-108">Условия, при которых отправляются пакеты протокола контроля транспорта в режиме реального времени (RTCP).</span><span class="sxs-lookup"><span data-stu-id="417b6-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="417b6-109">Требуется ли шифрование безопасного транспортного протокола реального времени (SRTP) на каждом магистрали.</span><span class="sxs-lookup"><span data-stu-id="417b6-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="417b6-110">При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="417b6-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="417b6-111">Эта глобальная коллекция параметров не подлежит удалению.</span><span class="sxs-lookup"><span data-stu-id="417b6-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="417b6-112">Однако вы можете использовать панель управления Skype для бизнес-серверов или группу [Remove-CsTrunkConfiguration,](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) чтобы "сбросить" свойства глобальной коллекции до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="417b6-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="417b6-113">Например, если задать свойство Enable3pccRefer как True, то при сбросе глобальной коллекции для свойства Enable3pccRefer возвращается значение по умолчанию False.</span><span class="sxs-lookup"><span data-stu-id="417b6-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="417b6-p103">Администраторы могут также создавать пользовательские параметры конфигурации магистральной линии для области сайта или службы (отдельного шлюза ТСОП); эти пользовательские параметры могут быть удалены. При удалении данных пользовательских параметров следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="417b6-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="417b6-p104">Если удалить параметры области службы, магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к их сайту, если эти параметры существуют. Если параметры сайта не существуют, эти магистральные линии будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="417b6-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="417b6-118">Если удалить параметры области сайта, любые магистральные линии SIP, управляемые этими параметрами, будут управляться глобальной коллекцией параметров конфигурации магистральной линии.</span><span class="sxs-lookup"><span data-stu-id="417b6-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="417b6-119">Удаление параметров конфигурации магистрали с панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="417b6-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="417b6-120">В панели управления Skype для бизнес-серверов щелкните **голосовую маршрутику** и нажмите кнопку **Конфигурация магистрали.**</span><span class="sxs-lookup"><span data-stu-id="417b6-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="417b6-p105">На вкладке **Настройка линии связи** выберите коллекцию параметров конфигурации магистральной линии SIP, которую следует удалить, щелкните **Изменить**, затем нажмите **Удалить**. Чтобы удалить несколько коллекций одновременно, щелкните первую удаляемую коллекцию, затем, удерживая нажатой клавишу Ctrl, щелкайте любые другие коллекции, которые следует удалить.</span><span class="sxs-lookup"><span data-stu-id="417b6-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="417b6-p106">Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="417b6-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="417b6-125">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="417b6-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="417b6-126">В **диалоговом окне Панель** управления Skype для бизнес-сервера нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="417b6-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="417b6-127">Если решено не удалять коллекцию, щелкните **Сохранить**, затем **Отменить все несохраненные изменения**.</span><span class="sxs-lookup"><span data-stu-id="417b6-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="417b6-128">Когда **появится диалоговое** окно Панели управления Skype для бизнес-серверов, нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="417b6-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="417b6-129">Удаление параметров конфигурации магистрали с помощью смещающихся кодлетов skype для управления бизнес-серверами</span><span class="sxs-lookup"><span data-stu-id="417b6-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="417b6-130">Параметры конфигурации магистрали можно удалить с помощью команды управления Skype для бизнес-серверов и команды **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="417b6-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="417b6-131">Этот комлет можно выполнить либо из оболочки управления Skype для бизнес-серверов, либо из удаленного сеанса команды Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="417b6-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="417b6-132">Удаление указанного собрания параметров</span><span class="sxs-lookup"><span data-stu-id="417b6-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="417b6-133">Следующая команда удаляет параметры конфигурации магистральной линии в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="417b6-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="417b6-134">Удаление всех коллекций, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="417b6-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="417b6-135">Эта команда удаляет все параметры конфигурации магистральной линии, примененные на уровне службы:</span><span class="sxs-lookup"><span data-stu-id="417b6-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="417b6-136">Удаление всех коллекций, в которых включен обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="417b6-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="417b6-137">Следующая команда удаляет все параметры конфигурации, где был включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="417b6-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="417b6-138">Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsTrunkConfiguration.](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="417b6-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
