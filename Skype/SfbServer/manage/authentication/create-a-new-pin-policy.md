---
title: Создание новой политики ПИН-кодов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: Сводка. Создание новой политики ПИН-кодов в Skype для бизнеса Server.
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828409"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="93ee7-103">Создание новой политики ПИН-кодов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93ee7-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="93ee7-104">**Сводка:** Создайте новую политику ПИН-кодов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93ee7-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="93ee7-105">Страницу политики  ПИН-кодов можно использовать для проверки подлинности с использованием пин-кода для пользователей, подключающихся к Skype для бизнеса с помощью IP-телефонов.</span><span class="sxs-lookup"><span data-stu-id="93ee7-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="93ee7-106">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="93ee7-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="93ee7-107">Для создания политики ПИН-кодов на уровне пользователя или сайта выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="93ee7-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="93ee7-108">Создание политики ПИН-кодов на уровне пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="93ee7-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="93ee7-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93ee7-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="93ee7-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93ee7-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="93ee7-111">В левой панели навигации последовательно выберите пункты **Security (Безопасность)** и **PIN Policy (Политика ПИН-кодов)**.</span><span class="sxs-lookup"><span data-stu-id="93ee7-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="93ee7-112">На странице **PIN Policy (Политика ПИН-кодов)** нажмите **New (Создать)**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="93ee7-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="93ee7-p102">Чтобы создать политику на уровне пользователя, выберите пункт **User policy (Политика пользователя)**. В разделе **New PIN Policy (Новая политика ПИН-кодов)**, в поле **Имя** укажите имя, которое описывает эту политику.</span><span class="sxs-lookup"><span data-stu-id="93ee7-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="93ee7-p103">Чтобы создать политику на уровне сайта, выберите пункт **Site policy (Политика сайта)**. В поле поиска **Select a Site (Выбор сайта)** введите имя (или часть имени) сайта, для которого требуется создать политику. В появившемся списке сайтов выберите нужный и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="93ee7-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="93ee7-118">В поле **Описание** введите описание этой политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="93ee7-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="93ee7-p104">В поле **Minimum PIN length (Минимальная длина ПИН-кода)** введите или выберите минимальную длину ПИН-кода, которую планируется разрешить. По умолчанию минимальная длина — пять цифр.</span><span class="sxs-lookup"><span data-stu-id="93ee7-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="93ee7-p105">Чтобы иметь возможность задавать максимальное количество попыток входа до блокировки пользователя, установите флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)**. Если этот флажок не установить, то максимальное количество разрешенных попыток определяется автоматически на основе длины ПИН-кода. По умолчанию максимальное количество попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="93ee7-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="93ee7-124">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="93ee7-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="93ee7-p106">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="93ee7-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="93ee7-128">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="93ee7-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="93ee7-p107">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="93ee7-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="93ee7-131">Чтобы разрешить распространенные шаблоны цифр в ПИН-коде, такие как "1234"  и "8888", выберите "Разрешить общие шаблоны".</span><span class="sxs-lookup"><span data-stu-id="93ee7-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="93ee7-132">Если этот флажок не установлен, то разрешены только сложные шаблоны цифр.</span><span class="sxs-lookup"><span data-stu-id="93ee7-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="93ee7-133">По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="93ee7-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="93ee7-134">Рекомендуется не разрешать простые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="93ee7-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="93ee7-135">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="93ee7-135">Click **Commit**.</span></span>
    

