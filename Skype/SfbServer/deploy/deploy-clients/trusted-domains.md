---
title: Доверенные домены системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Этот раздел содержит инструкции по настройке доверенных доменов для системы комнат Skype и Skype для бизнеса.
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768672"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="3bc26-103">Доверенные домены системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="3bc26-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="3bc26-104">Этот раздел содержит инструкции по настройке доверенных доменов для системы комнат Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3bc26-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="3bc26-105">Доверенные домены</span><span class="sxs-lookup"><span data-stu-id="3bc26-105">Trusted domains</span></span>

<span data-ttu-id="3bc26-106">Клиент Skype для бизнеса отображает диалоговое окно, в котором пользователи могут получить сертификат от сервера Skype для бизнеса, если домен SIP для входа в учетной записи пользователя отличается от имени в поле "Тема" или имени "Тема".</span><span class="sxs-lookup"><span data-stu-id="3bc26-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="3bc26-107">Если сертификат, настроенный для использования Skype для бизнеса Server в вашей организации, не имеет доменного имени SIP учетной записи системы комнаты Skype в поле "Тема" или имени для темы, необходимо настроить эти домены, которые представлены на сертификате в разделе "Доверенные домены". раздел реестра на компьютере, на котором находится консоль системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="3bc26-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="3bc26-108">Ваш изготовитель системы помещения в Skype — Руководство администратора системы для помещения в Skype, в котором описано, как и куда добавлять доверенные домены в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3bc26-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="3bc26-109">Например, предположим, что сертификаты, настроенные в Skype для бизнеса Server, имеют тему/тему с замещающим именем "CONTOSO. LOCAL ("confrm1@contoso.net") и один из доменов SIP, назначенных пользователю для системы комнатной комнаты Skype.</span><span class="sxs-lookup"><span data-stu-id="3bc26-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="3bc26-110">Так как contoso.net не находится в сертификате, на системном компьютере комнаты Skype необходимо настроить "contoso. local" как доверенный домен в реестре, как описано в разделе "Skype для вашего кабинета", предоставленном производителем системы помещения для Skype.</span><span class="sxs-lookup"><span data-stu-id="3bc26-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

