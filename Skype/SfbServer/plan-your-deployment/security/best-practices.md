---
title: Best practices for your core infrastructure in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Возможно, вы уже приняли меры для разработки системы обеспечения сбоя, используя такие методики, как обеспечение избыточности оборудования, обеспечение защиты от потери питания, регулярное установка обновлений системы безопасности и мер защиты от вирусов, а также действия сервера мониторинга. Эти методики будут использовать не только инфраструктуру Skype для бизнеса Server, но и всю сеть. Если вы не реализовали эти методики, рекомендуем сделать это перед развертыванием Skype для бизнеса Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832249"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="7b070-105">Best practices for your core infrastructure in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7b070-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="7b070-106">Возможно, вы уже приняли меры для разработки системы обеспечения сбоя, используя такие методики, как обеспечение избыточности оборудования, обеспечение защиты от потери питания, регулярное установка обновлений системы безопасности и мер защиты от вирусов, а также действия сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7b070-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="7b070-107">Эти методики будут использовать не только инфраструктуру Skype для бизнеса Server, но и всю сеть.</span><span class="sxs-lookup"><span data-stu-id="7b070-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="7b070-108">Если вы не реализовали эти методики, рекомендуем сделать это перед развертыванием Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b070-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="7b070-109">Чтобы защитить серверы в развертывании Skype для бизнеса Server от случайного или намеренного ущерба, который может привести к простою, примите следующие меры предосторожности:</span><span class="sxs-lookup"><span data-stu-id="7b070-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="7b070-110">Обновляйте серверы с помощью обновлений для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="7b070-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="7b070-111">Подписка на службу уведомлений о безопасности (Майкрософт) обеспечивает немедленное получение уведомлений о выпусках бюллетеней по безопасности для любого продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7b070-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="7b070-112">Чтобы подписаться, перейдите на [веб-сайт microsoft Technical Security Notifications.](https://go.microsoft.com/fwlink/p/?LinkId=145202)</span><span class="sxs-lookup"><span data-stu-id="7b070-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="7b070-113">Убедитесь, что права доступа настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="7b070-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="7b070-114">Храните серверы в физической среде, предотвращая несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="7b070-114">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="7b070-115">Убедитесь, что на всех серверах установлено соответствующее антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="7b070-115">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="7b070-116">Поддерживайте актуальность этого программного обеспечения установкой самых последних файлов сигнатур вирусов.</span><span class="sxs-lookup"><span data-stu-id="7b070-116">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="7b070-117">Используйте функцию автоматического обновления антивирусной программы для поддержания актуальности набора сигнатур вирусов.</span><span class="sxs-lookup"><span data-stu-id="7b070-117">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="7b070-118">Рекомендуется отключить службы операционной системы Windows Server, которые не требуются на компьютерах, на которых устанавливается Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b070-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="7b070-119">Шифруем операционные системы и диски, на которых хранятся данные, с помощью системы полного шифрования, если вы не можете гарантировать постоянный и полный контроль над серверами, полную физическую изоляцию, а также надлежащее и безопасное списание замененных или сбойных дисков.</span><span class="sxs-lookup"><span data-stu-id="7b070-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="7b070-120">Отключать все внешние порты прямого доступа к памяти (DMA) сервера, если вы не можете гарантировать очень жесткий контроль над физическим доступом к серверам.</span><span class="sxs-lookup"><span data-stu-id="7b070-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="7b070-121">Атаки на основе DMA, которые могут быть инициируются довольно легко, могут получить очень конфиденциальную информацию, например закрытые ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="7b070-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

