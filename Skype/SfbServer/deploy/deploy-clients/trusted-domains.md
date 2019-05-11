---
title: Доверенные домены системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Этот раздел содержит инструкции по настройке доверенных доменов для системы комнат Skype и Skype для бизнеса.
ms.openlocfilehash: ff8f75178fef21900292760fb71f53ea3746380c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895049"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="78bea-103">Доверенные домены системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="78bea-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="78bea-104">Этот раздел содержит инструкции по настройке доверенных доменов для системы комнат Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="78bea-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="78bea-105">Доверенные домены</span><span class="sxs-lookup"><span data-stu-id="78bea-105">Trusted domains</span></span>

<span data-ttu-id="78bea-106">Скайп для клиента Business отображает диалоговое окно для принятия сертификата из Скайп для Business Server, если домен SIP учетной записи пользователя для подписи отличается от имени, представленных в теме или Alt имя субъекта сертификата.</span><span class="sxs-lookup"><span data-stu-id="78bea-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="78bea-107">Если сертификат, настроенный для Скайп для Business Server в организации отсутствует имя домена SIP Скайп комнаты системной учетной записи в теме или Alt имя субъекта, необходимо настроить эти домены, представленные на сертификат в разделе доверенные домены раздел реестра на компьютере консоли Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="78bea-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="78bea-108">Руководство по системе комнаты Скайп предоставленного производителя Скайп комнаты системного администратора объясняется, как и где Добавление доверенных доменов в Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="78bea-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="78bea-109">Например предположим, что сертификаты, настроенные на Скайп для Business Server Name задано значение темы или темы Alt «CONTOSO. ЛОКАЛЬНЫЙ» и один из доменов SIP, назначенных пользователю для системы комнаты Скайп адрес для входа является «confrm1@contoso.net».</span><span class="sxs-lookup"><span data-stu-id="78bea-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="78bea-110">Так как contoso.net не в сертификат на компьютере Скайп комнаты системы, необходимо будет Настройка «contoso.local» в качестве доверенного домена в реестр, как описано в руководстве по системе комнаты Скайп предоставленного производителя Скайп комнаты системного администратора.</span><span class="sxs-lookup"><span data-stu-id="78bea-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

