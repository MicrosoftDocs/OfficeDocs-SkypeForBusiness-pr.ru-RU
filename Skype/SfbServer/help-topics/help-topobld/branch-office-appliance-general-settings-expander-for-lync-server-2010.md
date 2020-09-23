---
title: Расширитель общих настроек устройства для обеспечения связи в филиалах для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: Чтобы изменить свойства устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах, в разделе Общие необходимо настроить следующие параметры.
ms.openlocfilehash: 5bdcc283ce9f503af307e37a7c2f76c922d5facb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216160"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="18127-103">Расширитель общих настроек устройства для обеспечения связи в филиалах для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="18127-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="18127-104">Чтобы изменить свойства устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах, в разделе **Общие**необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="18127-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="18127-105">**Полное доменное**имя: введите полное доменное имя устройства или сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="18127-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="18127-106">**Использовать все настроенные IP-адреса** используют IP-адреса, настроенные на устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах, для всех целей.</span><span class="sxs-lookup"><span data-stu-id="18127-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="18127-107">**Ограничить использование службы выбранными IP-адресами**. Можно настроить определенный адрес для определения сервера и IP-адреса для связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="18127-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="18127-108">**Основной IP-адрес.** IP-адрес определяется и настраивается для всех зада, кроме функций, связанных с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="18127-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="18127-109">**IP-адрес для ТСОП**. IP-адрес, связанный с функциями ТСОП.</span><span class="sxs-lookup"><span data-stu-id="18127-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="18127-110">Вы настраиваете **связи** , чтобы убедиться, что другие роли сервера настроены и связаны с устройством для обеспечения связи в филиалах или с сервером обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="18127-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="18127-111">**Сопоставление сервера архивации** Выберите из списка сервер архивации, который необходимо связать с устройством для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="18127-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="18127-112">Нажмите кнопку **создать** , если вы не создали сервер архивации, который вы хотите сопоставить с этим устройством для обеспечения связи в филиалах или с сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="18127-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="18127-113">**Сопоставление сервера мониторинга** Выберите в списке Сервер мониторинга, который необходимо связать с устройством для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="18127-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="18127-114">Нажмите кнопку **создать** , если вы не создали сервер мониторинга, который вы хотите сопоставить с этим устройством для обеспечения связи в филиалах или с сервером обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="18127-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="18127-115">**Связать пограничный пул (для компонентов мультимедиа)** Выберите из списка пограничный сервер или пограничный пул, который необходимо связать с устройством для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="18127-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="18127-116">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="18127-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="18127-117">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="18127-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="18127-118">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="18127-118">**Help** Displays this help screen.</span></span>
  

