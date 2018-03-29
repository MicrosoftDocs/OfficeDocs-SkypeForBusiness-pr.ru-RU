---
title: Рекомендации по основной инфраструктуре в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Возможно, вы уже выполнили действия по проектированию отказоустойчивости вашей системы, применяя такие меры, как аппаратное резервирование, защита от потери напряжения питания, регулярная установка обновлений системы безопасности и использование средств защиты от вирусов, а также запуск сервера мониторинга. Эти рекомендации преимущества не только вашей Скайп для инфраструктуры Business Server, но всей сети. Если эти рекомендации не реализованы, рекомендуется делать это перед развертыванием Скайп для Business Server.
ms.openlocfilehash: 9d79f98ebc66807f21f8d1eef468efc400dd5fbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server-2015"></a><span data-ttu-id="57065-105">Рекомендации по основной инфраструктуре в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="57065-105">Best practices for your core infrastructure in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="57065-106">Возможно, вы уже выполнили действия по проектированию отказоустойчивости вашей системы, применяя такие меры, как аппаратное резервирование, защита от потери напряжения питания, регулярная установка обновлений системы безопасности и использование средств защиты от вирусов, а также запуск сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="57065-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="57065-107">Эти рекомендации преимущества не только вашей Скайп для инфраструктуры Business Server, но всей сети.</span><span class="sxs-lookup"><span data-stu-id="57065-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="57065-108">Если эти рекомендации не реализованы, рекомендуется делать это перед развертыванием Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="57065-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="57065-109">Для защиты серверов в вашей Скайп для развертывания Business Server от случайного или содержательные вред, который может привести к простою, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="57065-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="57065-110">Получайте последние обновления для системы безопасности на серверах.</span><span class="sxs-lookup"><span data-stu-id="57065-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="57065-111">Подписка на службу уведомлений безопасности Microsoft гарантирует, что вы получили немедленного бюллетеней по безопасности, выпущенные любого из продуктов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57065-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="57065-112">Для подписки, перейдите на [веб-сайте выпуске](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="57065-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="57065-113">Убедитесь, что настройка прав доступа выполнена правильно.</span><span class="sxs-lookup"><span data-stu-id="57065-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="57065-p104">Ваши серверы должны быть установлены в помещениях, исключающих несанкционированный доступ. Установите надежное антивирусное программное обеспечение на всех ваших серверах. Регулярно обновляйте файлы сигнатур вирусов антивирусного программного обеспечения. Для обеспечения актуальности файлов сигнатур вирусов активируйте функцию автоматического обновления в вашем антивирусном программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="57065-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="57065-118">Рекомендуется отключить службы операционной системы Windows Server, которые не требуется на компьютеры, где установлены Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="57065-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="57065-119">Зашифруйте операционные системы и дисковые устройства, на которых хранятся данные, с помощью полнодисковой системы шифрования, если вы не можете обеспечить постоянное и всестороннее управление серверами, их полную физическую изоляцию, а также надлежащий и безопасный вывод из эксплуатации замененных или отказавших дисковых устройств.</span><span class="sxs-lookup"><span data-stu-id="57065-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="57065-120">Отключите на серверах все внешние порты прямого доступа к памяти (DMA), если вы не можете гарантировать жесткий контроль за физическим доступом к серверам.</span><span class="sxs-lookup"><span data-stu-id="57065-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="57065-121">С помощью атак посредством прямого доступа к памяти, организовать которые достаточно просто, можно получить доступ к таким важным данным, как закрытые ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="57065-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

