---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Сводка: Узнайте, как удалить коллекцию параметров конфигурации магистрали с помощью Скайп для панели управления Business Server.'
ms.openlocfilehash: da86cbaf45afa47de580c02ab74e3b0b9bb344bf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890552"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="dcf0d-103">Удаление существующей коллекции параметров конфигурации магистрали SIP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="dcf0d-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="dcf0d-104">**Сводка:** Узнайте, как удалить коллекцию параметров конфигурации магистрали с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="dcf0d-p101">Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="dcf0d-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="dcf0d-107">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="dcf0d-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="dcf0d-108">условия, при которых отправляются пакеты протокола RTCP;</span><span class="sxs-lookup"><span data-stu-id="dcf0d-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="dcf0d-109">требуется ли использовать шифрование протокола SRTP для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="dcf0d-110">При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="dcf0d-111">Не удается удалить этот глобальной коллекции параметров.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="dcf0d-112">Тем не менее можно использовать Скайп для панели управления Business Server или командлет [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) «очистить» свойства в глобальную коллекцию значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="dcf0d-113">Например если задано свойство Enable3pccRefer имеет значение True, то при сбросе глобальную коллекцию свойство Enable3pccRefer восстановит в значение по умолчанию False.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="dcf0d-114">Администраторы могут также создавать настраиваемые магистрали параметров конфигурации на уровне сайта или на уровне службы (для отдельных шлюза ТСОП); Эти параметры можно удалить.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-114">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="dcf0d-115">При удалении этих настраиваемых параметров помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="dcf0d-115">When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="dcf0d-116">Если удалить параметры области действия службы, затем магистраль SIP, управляемые этими параметрами управляемые параметры, примененные к их сайта, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-116">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="dcf0d-117">Если параметры сайта не существует, эти магистралях затем будут управляться глобальной коллекции параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-117">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="dcf0d-118">Если удалить параметры области сайта выберите любые магистральные линии SIP, управляемые этими параметрами будут управляться глобальной коллекции параметров конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="dcf0d-119">Удаление параметров конфигурации магистрали с Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="dcf0d-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dcf0d-120">В Скайп для панели управления Business Server щелкните **Маршрутизация голосовой связи** и затем щелкните **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="dcf0d-121">На вкладке **Конфигурация магистрали** выберите коллекцию параметров конфигурации магистрали SIP, чтобы удалить, нажмите кнопку **Изменить** и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-121">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="dcf0d-122">Для удаления нескольких семейств сайтов в той же операции, нажмите кнопку первой коллекции, которую требуется удалить, а затем удерживайте нажатой клавишу Ctrl и щелкните любые дополнительные коллекции, которые вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-122">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="dcf0d-p106">Свойство **Состояние** для коллекции будет обновлено до **Не сохранено**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="dcf0d-125">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="dcf0d-126">В диалоговом окне **Скайп для панели управления Business Server** нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="dcf0d-127">Если решено не удалять семейство сайтов, нажмите кнопку **зафиксировать** и нажмите кнопку **Отмена всех незафиксированных изменений**окно.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="dcf0d-128">Когда появится диалоговое окно **Скайп для панели управления Business Server** , нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="dcf0d-129">Удаление параметров конфигурации магистрали с помощью Скайп по командлетам командной консоли управления Business Server</span><span class="sxs-lookup"><span data-stu-id="dcf0d-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="dcf0d-130">Параметры конфигурации можно удалить с помощью Скайп для консоли Business Server и в командлет **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="dcf0d-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="dcf0d-131">Можно запустить командлет из Скайп для консоли Business Server или из удаленного сеанса Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="dcf0d-132">Удаление указанной коллекции параметров</span><span class="sxs-lookup"><span data-stu-id="dcf0d-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="dcf0d-133">Следующая команда удаляет параметры конфигурации, применяемые к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="dcf0d-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="dcf0d-134">Удаление всех коллекций, примененных на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="dcf0d-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="dcf0d-135">Эта команда удаляет все параметры конфигурации магистральной линии связи, применяемых на уровне службы:</span><span class="sxs-lookup"><span data-stu-id="dcf0d-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="dcf0d-136">Чтобы удалить все семейства сайтов, где сервера-посредника включена</span><span class="sxs-lookup"><span data-stu-id="dcf0d-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="dcf0d-137">Следующая команда удаляет все параметры конфигурации, где сервера-посредника был включен.</span><span class="sxs-lookup"><span data-stu-id="dcf0d-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="dcf0d-138">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="dcf0d-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

