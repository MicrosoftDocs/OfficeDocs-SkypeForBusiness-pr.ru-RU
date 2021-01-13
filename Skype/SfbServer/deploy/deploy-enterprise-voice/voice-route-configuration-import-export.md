---
title: Экспорт или импорт файла конфигурации маршрута голосовых вызовов в Skype для бизнеса
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: Сводка. Узнайте, как экспортировать или импортировать файл конфигурации маршрутки голосовой почты в Skype для бизнеса Server с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830359"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="59421-103">Экспорт или импорт файла конфигурации маршрута голосовых вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="59421-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="59421-104">**Сводка:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="59421-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="59421-105">Если вы хотите сохранить конфигурацию маршрутации голосовых данных без ее публикации, выполните следующие действия, чтобы сохранить и получить снимок конфигурации маршрутации голосовых данных.</span><span class="sxs-lookup"><span data-stu-id="59421-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="59421-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span><span class="sxs-lookup"><span data-stu-id="59421-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="59421-107">Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.</span><span class="sxs-lookup"><span data-stu-id="59421-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="59421-108">Если вы влияли на параметры на любой странице группы, изменения сохраняются в экспортируемом файле конфигурации голосовой связи (VCFG).</span><span class="sxs-lookup"><span data-stu-id="59421-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="59421-109">Это позволяет внести изменения в конфигурацию маршрутации голосовой связи во время нескольких сеансов перед публикацией изменений.</span><span class="sxs-lookup"><span data-stu-id="59421-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="59421-110">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="59421-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="59421-111">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="59421-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="59421-112">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="59421-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="59421-113">В левой панели навигации щелкните элемент **Маршрутизация голосовых данных**.</span><span class="sxs-lookup"><span data-stu-id="59421-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="59421-114">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="59421-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="59421-115">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="59421-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="59421-116">Импорт конфигурации маршрутации голосовой почты</span><span class="sxs-lookup"><span data-stu-id="59421-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="59421-117">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="59421-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="59421-118">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="59421-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="59421-119">В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="59421-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="59421-120">В меню **"Действия"** выберите пункт **"Импорт конфигурации".**</span><span class="sxs-lookup"><span data-stu-id="59421-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="59421-121">Найдите файл конфигурации, который нужно импортировать, и нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="59421-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="59421-122">Нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="59421-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59421-123">При импорте файла конфигурации голосовой почты необходимо выполнить команду **"Зафиксировать все",** чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="59421-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="59421-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="59421-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

