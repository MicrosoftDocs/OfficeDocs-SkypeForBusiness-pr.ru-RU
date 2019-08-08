---
title: Экспорт и импорт файла конфигурации голосового маршрута в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: Сводка. сведения о том, как экспортировать или импортировать файл конфигурации голосовой связи в Skype для бизнеса Server с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239917"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="cfd05-103">Экспорт и импорт файла конфигурации голосового маршрута в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cfd05-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="cfd05-104">**Сводка:** Сведения о том, как экспортировать или импортировать файл конфигурации голосовой связи в Skype для бизнеса Server можно с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cfd05-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="cfd05-105">Если требуется сохранить конфигурацию маршрутизации голосовых данных без ее публикации, выполните следующие действия для сохранения и извлечения снимков конфигурации маршрутизации голосовых данных.</span><span class="sxs-lookup"><span data-stu-id="cfd05-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="cfd05-106">При импорте файла конфигурации голосовой маршрутизации (. вкфг) изменения, внесенные в конфигурацию маршрутизации голоса на сервере, будут указывать на то, что на панели управления "Маршрутизация \*\*\*\* голосовых сообщений" в Skype для бизнеса Server — Это незафиксированные изменения в маршруте голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cfd05-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="cfd05-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span><span class="sxs-lookup"><span data-stu-id="cfd05-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="cfd05-108">Если вы внесли какие-либо незафиксированные изменения параметров на любой странице в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="cfd05-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="cfd05-109">Это позволит вам вносить изменения в конфигурацию голосовой маршрутизации во время нескольких сеансов, прежде чем публиковать изменения.</span><span class="sxs-lookup"><span data-stu-id="cfd05-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="cfd05-110">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="cfd05-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="cfd05-111">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="cfd05-112">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cfd05-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cfd05-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="cfd05-114">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="cfd05-115">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="cfd05-116">Импорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="cfd05-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="cfd05-117">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="cfd05-118">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cfd05-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cfd05-119">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="cfd05-120">В меню **Действия** щелкните пункт **Импорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="cfd05-121">Найдите импортируемый файл конфигурации и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="cfd05-122">Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="cfd05-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cfd05-123">При каждом импорте файла конфигурации голосовой связи вам следует запускать команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfd05-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cfd05-124">Дополнительные сведения можно найти в разделе [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса](voice-route-config-changes.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="cfd05-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

