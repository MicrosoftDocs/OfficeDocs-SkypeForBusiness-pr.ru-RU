---
title: Экспортировать или импортировать файл конфигурации маршрутизации голосовой связи в Скайп для бизнеса
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Сводка: Узнайте, как экспортировать или импортировать файл конфигурации маршрутизации голосовой связи в Скайп для Business Server с помощью Скайп для панели управления Business Server.'
ms.openlocfilehash: 5cf9021a1cc18daf90fc719723962959142ad92e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886791"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="c3707-103">Экспортировать или импортировать файл конфигурации маршрутизации голосовой связи в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c3707-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="c3707-104">**Сводка:** Узнайте, как экспортировать или импортировать файл конфигурации маршрутизации голосовой связи в Скайп для Business Server с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3707-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="c3707-105">Если требуется сохранить конфигурацию маршрутизации голосовых данных без ее публикации, выполните следующие действия для сохранения и извлечения снимков конфигурации маршрутизации голосовых данных.</span><span class="sxs-lookup"><span data-stu-id="c3707-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="c3707-106">При импорте файла конфигурации маршрутизации голосовой связи (.vcfg), но изменений конфигурации маршрутизации голосовых данных на сервере в это время, страницы в группе **Маршрутизации голосовой связи** в Скайп для панели управления Business Server будет указать, что существует все незафиксированные изменения на голосовую маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c3707-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="c3707-107">Эти несохраненные изменения, различия между двумя конфигураций, которые требуют Выверка.</span><span class="sxs-lookup"><span data-stu-id="c3707-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="c3707-108">Если были внесены несохраненные изменения параметров на любую страницу в группе, изменения будут сохранены в файле конфигурации экспортированного голосовой связи (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="c3707-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="c3707-109">Это позволяет внести изменения конфигурации маршрутизации во время нескольких сеансов перед публикацией изменений голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c3707-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="c3707-110">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="c3707-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="c3707-111">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="c3707-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="c3707-112">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3707-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c3707-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c3707-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="c3707-114">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="c3707-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="c3707-115">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c3707-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="c3707-116">Импорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="c3707-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="c3707-117">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="c3707-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="c3707-118">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3707-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c3707-119">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c3707-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="c3707-120">В меню **Действия** щелкните пункт **Импорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="c3707-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="c3707-121">Найдите импортируемый файл конфигурации и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="c3707-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="c3707-122">Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="c3707-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3707-123">При каждом импорте файла конфигурации голосовой связи вам следует запускать команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3707-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c3707-124">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="c3707-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

