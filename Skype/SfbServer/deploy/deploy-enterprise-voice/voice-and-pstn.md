---
title: Настройка политик голосовой почты, записей использования PSTN и маршрутов голосовых вызовов в Skype для бизнеса
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: Сводка. Узнайте, как настроить политики голосовой почты, записи использования ЗВОНКОВ и маршруты голосовых вызовов в Skype для бизнеса Server.
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830451"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="05fb7-103">Настройка политик голосовой почты, записей использования PSTN и маршрутов голосовых вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05fb7-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="05fb7-104">**Сводка:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="05fb7-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="05fb7-p101">Политики голосовой связи, записи использования ТСОП и маршруты голосовых вызовов тесно связаны. Вы настраиваете политики голосовой связи, выбирая набор возможностей звонков и назначая политике набор записей использования ТСОП, указывающих, какие права разрешены для пользователей или групп, которым назначена политика голосовой связи. Маршрутам голосовых вызовов также назначаются записи использования ТСОП, служащие для сопоставления маршрутов с пользователями, которым разрешено эти маршруты использовать. Таким образом, пользователи могут выполнять только звонки, использующие маршруты, для которых имеется соответствующая запись использования ТСОП.</span><span class="sxs-lookup"><span data-stu-id="05fb7-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="05fb7-109">Рекомендуемый рабочий процесс для нового развертывания корпоративной голосовой связи заключается в том, чтобы начать с настройки политики голосовой связи, включающей в себя подходящие записи использования ТСОП, а затем сопоставить соответствующие маршруты с каждой из записей использования ТСОП.</span><span class="sxs-lookup"><span data-stu-id="05fb7-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="05fb7-110">Можно также создать политики голосовой связи с  *областью*  действия пользователя и назначить их отдельным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="05fb7-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="05fb7-111">Подробные сведения о выполнении каждой из этих задач см. процедуры, приведенные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="05fb7-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="05fb7-112">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="05fb7-112">In this section</span></span>

- [<span data-ttu-id="05fb7-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="05fb7-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="05fb7-114">Настройка escape-сообщения голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05fb7-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="05fb7-115">Просмотр записей об использовании ЗВОНКОВ в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05fb7-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="05fb7-116">Создание или изменение маршрута голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05fb7-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="05fb7-117">Экспорт или импорт файла конфигурации маршрута голосовых вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05fb7-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="05fb7-118">Публикация ожидающих изменений в конфигурации маршрутации голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05fb7-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

