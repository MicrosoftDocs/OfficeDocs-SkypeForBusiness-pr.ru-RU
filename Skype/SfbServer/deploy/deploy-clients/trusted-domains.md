---
title: Доверенные домены системы комнат Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: В этом разделе вы узнаете, как настроить доверенные домены для системы комнат Skype и Skype для бизнеса.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834119"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="e24df-103">Доверенные домены системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="e24df-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="e24df-104">В этом разделе вы узнаете, как настроить доверенные домены для системы комнат Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e24df-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="e24df-105">Доверенные домены</span><span class="sxs-lookup"><span data-stu-id="e24df-105">Trusted domains</span></span>

<span data-ttu-id="e24df-106">Клиент Skype для бизнеса отображает диалоговое окно, которое позволяет пользователям принимать сертификат из Skype для бизнеса Server, если домен SIP учетной записи, в которую вошел пользователь, отличается от имени, представленного в поле "Субъект" или "Имя субъекта" сертификата.</span><span class="sxs-lookup"><span data-stu-id="e24df-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="e24df-107">Если сертификат, настроенный для Skype для бизнеса Server в вашей организации, не имеет доменного имени SIP учетной записи системы комнат Skype в субъекте или замеите субъекта, необходимо настроить эти домены, представленные в сертификате в ключе реестра доверенных доменов на компьютере консоли системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e24df-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="e24df-108">Руководство администратора системы комнат Skype, предоставленное производителем системы комнат Skype, объясняет, как и где добавлять доверенные домены в клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e24df-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="e24df-109">Например, предположим, что сертификаты, настроенные в Skype для бизнеса Server, имеют заме-имя субъекта/субъекта "CONTOSO". LOCAL и один из доменов SIP, присвоенных пользователю для адреса для входов в систему комнат Skype, имеет confrm1@contoso.net.</span><span class="sxs-lookup"><span data-stu-id="e24df-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="e24df-110">Поскольку contoso.net нет в сертификате, на компьютере системы комнат Skype необходимо настроить contoso.local в качестве доверенного домена в реестре, как поясняется в руководстве администратора системы комнат Skype, предоставленном производителем системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e24df-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

