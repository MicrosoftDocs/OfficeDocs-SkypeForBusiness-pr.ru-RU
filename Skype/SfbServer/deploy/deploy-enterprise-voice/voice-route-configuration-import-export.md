---
title: Экспорт и импорт файла конфигурации маршрута голосовой связи в Skype для бизнеса 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Сводка: Узнайте, как экспортировать или импортировать файл конфигурации маршрутизации голосовой связи в Скайп для Business Server 2015 с помощью Скайп для панели управления Business Server.'
ms.openlocfilehash: ba16e68ec3218a06d1baf21c238b14e3f566f630
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a><span data-ttu-id="31b21-103">Экспорт и импорт файла конфигурации маршрута голосовой связи в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="31b21-103">Export or import a voice route configuration file in Skype for Business 2015</span></span>
 
<span data-ttu-id="31b21-104">**Сводка:** Узнайте, как экспортировать или импортировать файл конфигурации маршрутизации голосовой связи в Скайп для Business Server 2015 с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="31b21-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="31b21-105">Если требуется сохранить конфигурацию маршрутизации голосовых данных без ее публикации, выполните следующие действия для сохранения и извлечения снимков конфигурации маршрутизации голосовых данных.</span><span class="sxs-lookup"><span data-stu-id="31b21-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="31b21-106">При импорте файла конфигурации маршрутизации голосовой связи (.vcfg), но изменений конфигурации маршрутизации голосовых данных на сервере в это время, страницы в группе **Маршрутизации голосовой связи** в Скайп для панели управления Business Server будет указать, что существует все незафиксированные изменения на голосовую маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="31b21-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="31b21-107">Эти несохраненные изменения, различия между двумя конфигураций, которые требуют Выверка.</span><span class="sxs-lookup"><span data-stu-id="31b21-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="31b21-108">Если были внесены несохраненные изменения параметров на любую страницу в группе, изменения будут сохранены в файле конфигурации экспортированного голосовой связи (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="31b21-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="31b21-109">Это позволяет внести изменения конфигурации маршрутизации во время нескольких сеансов перед публикацией изменений голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="31b21-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="31b21-110">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="31b21-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="31b21-111">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="31b21-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="31b21-112">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="31b21-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="31b21-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="31b21-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="31b21-114">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="31b21-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="31b21-115">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="31b21-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="31b21-116">Импорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="31b21-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="31b21-117">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="31b21-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="31b21-118">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="31b21-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="31b21-119">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="31b21-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="31b21-120">В меню **Действия** щелкните пункт **Импорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="31b21-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="31b21-121">Найдите импортируемый файл конфигурации и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="31b21-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="31b21-122">Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="31b21-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="31b21-123">При каждом импорте файла конфигурации голосовой связи вам следует запускать команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="31b21-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="31b21-124">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для 2015 бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="31b21-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

