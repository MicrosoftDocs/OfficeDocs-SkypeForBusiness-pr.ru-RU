---
title: Рекомендации для базовой инфраструктуры в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Возможно, вы уже выполнили действия по проектированию отказоустойчивости вашей системы, применяя такие меры, как аппаратное резервирование, защита от потери напряжения питания, регулярная установка обновлений системы безопасности и использование средств защиты от вирусов, а также запуск сервера мониторинга. Эти практические рекомендации не только для инфраструктуры Skype для бизнеса Server, но и для всей сети. Если вы не реализовали эти рекомендации, рекомендуем сделать это перед развертыванием Skype для бизнеса Server.
ms.openlocfilehash: c1f6a6ebe31276b8dbcd9037fa373baffc055fde
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296968"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="eb031-105">Рекомендации для базовой инфраструктуры в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="eb031-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="eb031-106">Возможно, вы уже выполнили действия по проектированию отказоустойчивости вашей системы, применяя такие меры, как аппаратное резервирование, защита от потери напряжения питания, регулярная установка обновлений системы безопасности и использование средств защиты от вирусов, а также запуск сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="eb031-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="eb031-107">Эти практические рекомендации не только для инфраструктуры Skype для бизнеса Server, но и для всей сети.</span><span class="sxs-lookup"><span data-stu-id="eb031-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="eb031-108">Если вы не реализовали эти рекомендации, рекомендуем сделать это перед развертыванием Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eb031-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="eb031-109">Чтобы защитить серверы в развертывании сервера Skype для бизнеса и случайно или целенаправленная причин, которые могут привести к простою, примите следующие меры предосторожности.</span><span class="sxs-lookup"><span data-stu-id="eb031-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="eb031-110">Обновляйте свои серверы с помощью обновлений для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb031-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="eb031-111">Подписка на Microsoft Security Notification Service гарантирует получение немедленного уведомления о выпусках бюллетеней безопасности для любого продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eb031-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="eb031-112">Чтобы подписаться на подписку, перейдите на [веб-сайт уведомлений Майкрософт по технической безопасности](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="eb031-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="eb031-113">Убедитесь, что настройка прав доступа выполнена правильно.</span><span class="sxs-lookup"><span data-stu-id="eb031-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="eb031-p104">Ваши серверы должны быть установлены в помещениях, исключающих несанкционированный доступ. Установите надежное антивирусное программное обеспечение на всех ваших серверах. Регулярно обновляйте файлы сигнатур вирусов антивирусного программного обеспечения. Для обеспечения актуальности файлов сигнатур вирусов активируйте функцию автоматического обновления в вашем антивирусном программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="eb031-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="eb031-118">Мы рекомендуем отключить службы операционной системы Windows Server, которые не требуются на компьютерах, на которых вы установили Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eb031-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="eb031-119">Зашифруйте операционные системы и дисковые устройства, на которых хранятся данные, с помощью полнодисковой системы шифрования, если вы не можете обеспечить постоянное и всестороннее управление серверами, их полную физическую изоляцию, а также надлежащий и безопасный вывод из эксплуатации замененных или отказавших дисковых устройств.</span><span class="sxs-lookup"><span data-stu-id="eb031-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="eb031-120">Отключите на серверах все внешние порты прямого доступа к памяти (DMA), если вы не можете гарантировать жесткий контроль за физическим доступом к серверам.</span><span class="sxs-lookup"><span data-stu-id="eb031-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="eb031-121">С помощью атак посредством прямого доступа к памяти, организовать которые достаточно просто, можно получить доступ к таким важным данным, как закрытые ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="eb031-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

