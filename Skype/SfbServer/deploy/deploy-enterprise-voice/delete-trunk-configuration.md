---
title: Удаление существующей коллекции параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Сводка. сведения о том, как удалить набор параметров конфигурации магистрали с помощью панели управления "Skype для бизнеса Server".
ms.openlocfilehash: 1cd46f855a92f4b1b975f565b12ff07c3af24111
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767712"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9b41c-103">Удаление существующей коллекции параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9b41c-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9b41c-104">**Сводка:** Сведения о том, как удалить набор параметров конфигурации магистрали с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b41c-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="9b41c-p101">Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="9b41c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="9b41c-107">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="9b41c-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="9b41c-108">условия, при которых отправляются пакеты протокола RTCP;</span><span class="sxs-lookup"><span data-stu-id="9b41c-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="9b41c-109">требуется ли использовать шифрование протокола SRTP для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="9b41c-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="9b41c-110">При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="9b41c-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="9b41c-111">Этот глобальный набор параметров нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="9b41c-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="9b41c-112">Тем не менее, вы можете использовать серверную панель управления Skype для бизнеса или командлет [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) для восстановления значений по умолчанию для свойств в глобальной коллекции.</span><span class="sxs-lookup"><span data-stu-id="9b41c-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="9b41c-113">Например, если для свойства Enable3pccRefer задано значение "true", при сбросе глобальной коллекции к значению по умолчанию для свойства Enable3pccRefer будет возвращено значение false.</span><span class="sxs-lookup"><span data-stu-id="9b41c-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="9b41c-114">Кроме того, администраторы могут создавать пользовательские параметры для настройки магистрали в области сайта или в области обслуживания (для отдельного шлюза PSTN); Эти пользовательские параметры можно удалить.</span><span class="sxs-lookup"><span data-stu-id="9b41c-114">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="9b41c-115">При удалении этих настраиваемых параметров следует учитывать указанные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="9b41c-115">When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="9b41c-116">Если вы удалите параметры области службы, то магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к своему сайту (если они существуют).</span><span class="sxs-lookup"><span data-stu-id="9b41c-116">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="9b41c-117">Если параметр "Параметры сайта" не существует, эти магистрали будут управляться глобальной коллекцией параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="9b41c-117">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="9b41c-118">После удаления параметров уровня сайта все магистральные элементы SIP, управляемые этими параметрами, теперь будут управляться глобальной коллекцией параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="9b41c-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="9b41c-119">Удаление параметров конфигурации канала с помощью панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="9b41c-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9b41c-120">На панели управления Skype для бизнеса Server щелкните **Маршрутизация голосовой связи** и выберите **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="9b41c-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="9b41c-121">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистральной магистрали, которые нужно удалить, и нажмите кнопку **изменить** , а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="9b41c-121">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="9b41c-122">Чтобы удалить несколько коллекций в одной операции, щелкните первую из них, которую нужно удалить, а затем, удерживая нажатой клавишу CTRL, щелкните все дополнительные коллекции, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="9b41c-122">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="9b41c-p106">Свойство **Состояние** для коллекции будет обновлено до **Не сохранено**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="9b41c-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="9b41c-125">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9b41c-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="9b41c-126">В диалоговом окне " **Панель управления" в Skype для бизнеса Server** нажмите кнопку " **ОК**".</span><span class="sxs-lookup"><span data-stu-id="9b41c-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="9b41c-127">Если вы передумали и решили не удалять коллекцию, нажмите кнопку **сохранить** , а затем — **отменить все незафиксированные изменения**.</span><span class="sxs-lookup"><span data-stu-id="9b41c-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="9b41c-128">Когда появится диалоговое окно " **Панель управления" в Skype для бизнеса Server** , нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9b41c-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="9b41c-129">Удаление параметров конфигурации магистрали с помощью командлетов командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9b41c-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="9b41c-130">Вы можете удалить параметры конфигурации канала с помощью командной консоли Skype для бизнеса Server и командлета **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9b41c-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="9b41c-131">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b41c-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="9b41c-132">Удаление заданной коллекции параметров</span><span class="sxs-lookup"><span data-stu-id="9b41c-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="9b41c-133">Следующая команда удаляет параметры конфигурации магистрали, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="9b41c-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="9b41c-134">Удаление всех коллекций, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="9b41c-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="9b41c-135">Эта команда удаляет все параметры конфигурации канала, примененные к области обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9b41c-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="9b41c-136">Удаление всех коллекций с включенным обходом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="9b41c-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="9b41c-137">Следующая команда удаляет все параметры конфигурации канала, в которых включен обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9b41c-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="9b41c-138">Дополнительные сведения можно найти в разделе справки по командлету [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9b41c-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

