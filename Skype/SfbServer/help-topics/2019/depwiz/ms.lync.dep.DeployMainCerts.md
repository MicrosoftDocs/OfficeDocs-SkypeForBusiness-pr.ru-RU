---
title: Запрос, установка или назначение сертификатов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: Шаг 3. запрос, установка и назначение сертификатов. Запуск мастера сертификатов после нажатия кнопки выполнить. Сертификаты, настроенные с помощью мастера, основываются на определении топологии сервера Skype для бизнеса, которая настроена и Опубликовано построителем топологии в хранилище Центрального управления. Для успешного запуска мастера сертификатов в Интернет-центре сертификации необходимо войти в систему с учетной записью пользователя, который является членом группы локальных администраторов компьютера. Кроме того, необходимо иметь учетную запись пользователя домена, прошедшего проверку подлинности, в домене, где есть компьютер и центр сертификации. Мастер сертификатов предоставляет возможность указывать альтернативные учетные данные для доступа к центру сертификации организации.
ms.openlocfilehash: faf6fa63770d27c90a94c01753d99a079cb5ef28
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299013"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="9590d-107">Запрос, установка или назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="9590d-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="9590d-108">**Шаг 3. запрос, установка и назначение сертификатов** . Запуск мастера сертификатов после нажатия кнопки **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="9590d-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="9590d-109">Сертификаты, настроенные с помощью мастера, основываются на определении топологии сервера Skype для бизнеса, которая настроена и Опубликовано построителем топологии в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="9590d-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="9590d-110">Для успешного запуска мастера сертификатов в Интернет-центре сертификации необходимо войти в систему с учетной записью пользователя, который является членом группы локальных администраторов компьютера.</span><span class="sxs-lookup"><span data-stu-id="9590d-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="9590d-111">Кроме того, необходимо иметь учетную запись пользователя домена, прошедшего проверку подлинности, в домене, где есть компьютер и центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="9590d-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="9590d-112">Мастер сертификатов предоставляет возможность указывать альтернативные учетные данные для доступа к центру сертификации организации.</span><span class="sxs-lookup"><span data-stu-id="9590d-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9590d-p103">С помощью мастера сертификатов можно также создавать и обрабатывать автономные запросы сертификатов, отправляемые в общий центр сертификации или другую автономную инфраструктуру открытых ключей (PKI). Для создания автономного запроса нет специального уровня участия помимо того, который необходим для входа в компьютер. Для обработки ответа общего центра сертификации и назначения сертификата компьютеру и роли вы должны войти в компьютер как участник локальной группы администраторов или эквивалентный ему пользователь.</span><span class="sxs-lookup"><span data-stu-id="9590d-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

