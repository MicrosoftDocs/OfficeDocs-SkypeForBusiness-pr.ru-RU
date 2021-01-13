---
title: Запрос, установка или назначение сертификатов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: Шаг 3. При нажатии кнопки "Выполнить" запускается мастер сертификатов запроса, установки или назначения сертификатов. Сертификаты, настроенные с помощью мастера, основаны на определении топологии Skype для бизнеса Server, настроенной и опубликованной построив топологий в центральном хранилище управления. Чтобы успешно запустить мастер сертификатов для веб-цс сертификации в организации, необходимо войти на компьютер в качестве пользователя, который является членом группы локальных администраторов компьютера. Вы также должны быть пользователем домена с проверкой подлинности в домене, в котором существуют компьютер и ЦС. Мастер сертификатов предоставляет возможность указать альтернативные учетные данные для доступа к ЦС организации.
ms.openlocfilehash: ec611ee92e26923da45602055771b85fb8cc9a55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825019"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="0e3ce-107">Запрос, установка или назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="0e3ce-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="0e3ce-108">**Шаг 3. При нажатии** кнопки "Выполнить" запускается мастер сертификатов запроса, установки или назначения **сертификатов.**</span><span class="sxs-lookup"><span data-stu-id="0e3ce-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="0e3ce-109">Сертификаты, настроенные с помощью мастера, основаны на определении топологии Skype для бизнеса Server, настроенной и опубликованной построив топологий в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="0e3ce-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="0e3ce-110">Чтобы успешно запустить мастер сертификатов для интерактивного ЦС в организации, необходимо войти на компьютер в качестве пользователя, который является членом группы локальных администраторов компьютера.</span><span class="sxs-lookup"><span data-stu-id="0e3ce-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="0e3ce-111">Вы также должны быть пользователем домена с проверкой подлинности в домене, в котором существуют компьютер и ЦС.</span><span class="sxs-lookup"><span data-stu-id="0e3ce-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="0e3ce-112">Мастер сертификатов предоставляет возможность указать альтернативные учетные данные для доступа к ЦС организации.</span><span class="sxs-lookup"><span data-stu-id="0e3ce-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e3ce-p103">С помощью мастера сертификатов можно также создавать и обрабатывать автономные запросы сертификатов, отправляемые в общий центр сертификации или другую автономную инфраструктуру открытых ключей (PKI). Для создания автономного запроса нет специального уровня участия помимо того, который необходим для входа в компьютер. Для обработки ответа общего центра сертификации и назначения сертификата компьютеру и роли вы должны войти в компьютер как участник локальной группы администраторов или эквивалентный ему пользователь.</span><span class="sxs-lookup"><span data-stu-id="0e3ce-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

