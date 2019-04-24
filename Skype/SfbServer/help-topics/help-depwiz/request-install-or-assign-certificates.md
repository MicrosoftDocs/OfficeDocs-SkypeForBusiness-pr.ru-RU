---
title: Запрос, установка или назначение сертификатов
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: 'Шаг 3: Запрос, установка или назначение сертификатов запускается мастер сертификатов после выберите пункт выполнить. Сертификаты, настроенные в мастере основаны на определении Скайп для топологии Business Server 2015, настроена и опубликованный Topology Builder для центрального хранилища управления. Для успешного запуска мастера сертификатов для локальную службу сертификации (ЦС) в организации, необходимо войти на компьютер как пользователь, являющийся членом группы администраторов локального компьютера. Также необходимо прошедшего проверку подлинности пользователя домена в домене, где существует компьютера и ЦС. Мастер сертификатов предоставляют возможность указать альтернативные учетные данные для доступа к ЦС организации.'
ms.openlocfilehash: 616e370663a2cee1b067b31cfd04ae2d1fc9e323
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201197"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="8f88b-107">Запрос, установка или назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="8f88b-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="8f88b-108">**Шаг 3: запрос, установка или назначение сертификатов** запускает мастер сертификатов при нажатии кнопки **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8f88b-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="8f88b-109">Сертификаты, настроенные в мастере основаны на определении Скайп для топологии Business Server 2015, настроена и опубликованный Topology Builder для центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="8f88b-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="8f88b-110">Для успешного запуска мастера сертификатов для локальную службу сертификации (ЦС) в организации, необходимо войти на компьютер как пользователь, являющийся членом группы администраторов локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="8f88b-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="8f88b-111">Также необходимо прошедшего проверку подлинности пользователя домена в домене, где существует компьютера и ЦС.</span><span class="sxs-lookup"><span data-stu-id="8f88b-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="8f88b-112">Мастер сертификатов предоставляют возможность указать альтернативные учетные данные для доступа к ЦС организации.</span><span class="sxs-lookup"><span data-stu-id="8f88b-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f88b-p103">С помощью мастера сертификатов можно также создавать и обрабатывать автономные запросы сертификатов, отправляемые в общий центр сертификации или другую автономную инфраструктуру открытых ключей (PKI). Для создания автономного запроса нет специального уровня участия помимо того, который необходим для входа в компьютер. Для обработки ответа общего центра сертификации и назначения сертификата компьютеру и роли вы должны войти в компьютер как участник локальной группы администраторов или эквивалентный ему пользователь.</span><span class="sxs-lookup"><span data-stu-id="8f88b-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

