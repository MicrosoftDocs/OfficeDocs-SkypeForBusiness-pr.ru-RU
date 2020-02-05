---
title: Экспорт и импорт файла конфигурации голосового маршрута в Skype для бизнеса
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: Сводка. сведения о том, как экспортировать или импортировать файл конфигурации голосовой связи в Skype для бизнеса Server с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: b980aa26f4d67cd1697ec17286e6af7d9e657e15
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766882"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="ecc18-103">Экспорт и импорт файла конфигурации голосового маршрута в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ecc18-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="ecc18-104">**Сводка:** Сведения о том, как экспортировать или импортировать файл конфигурации голосовой связи в Skype для бизнеса Server можно с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ecc18-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="ecc18-105">Если требуется сохранить конфигурацию маршрутизации голосовых данных без ее публикации, выполните следующие действия для сохранения и извлечения снимков конфигурации маршрутизации голосовых данных.</span><span class="sxs-lookup"><span data-stu-id="ecc18-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="ecc18-106">При импорте файла конфигурации голосовой маршрутизации (. вкфг) изменения, внесенные в конфигурацию маршрутизации голосовых сообщений на сервере, будут указывать на наличие незафиксированных изменений, внесенных в голосовую почту, в группе " **Маршрутизация** голосовой связи" на панели управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="ecc18-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="ecc18-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span><span class="sxs-lookup"><span data-stu-id="ecc18-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="ecc18-108">Если вы внесли какие-либо незафиксированные изменения параметров на любой странице в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="ecc18-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="ecc18-109">Это позволит вам вносить изменения в конфигурацию голосовой маршрутизации во время нескольких сеансов, прежде чем публиковать изменения.</span><span class="sxs-lookup"><span data-stu-id="ecc18-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="ecc18-110">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="ecc18-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="ecc18-111">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ecc18-112">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ecc18-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ecc18-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="ecc18-114">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="ecc18-115">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="ecc18-116">Импорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="ecc18-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="ecc18-117">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ecc18-118">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ecc18-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ecc18-119">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="ecc18-120">В меню **Действия** щелкните пункт **Импорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="ecc18-121">Найдите импортируемый файл конфигурации и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="ecc18-122">Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="ecc18-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ecc18-123">При каждом импорте файла конфигурации голосовой связи вам следует запускать команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ecc18-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ecc18-124">Дополнительные сведения можно найти в разделе [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса](voice-route-config-changes.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="ecc18-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

