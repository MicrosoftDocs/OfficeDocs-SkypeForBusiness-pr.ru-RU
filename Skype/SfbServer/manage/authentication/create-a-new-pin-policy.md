---
title: Создание новой политики ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Сводка: создание новой политики ПИН-кода в Skype для бизнеса Server.'
ms.openlocfilehash: 46464962ea53d81978f0d345d63e380a677b152f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818811"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="532d7-103">Создание новой политики ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="532d7-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="532d7-104">**Сводка:** Создайте новую политику закрепления в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532d7-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="532d7-105">Вы можете использовать страницу **политики ПИН** для предоставления персонального идентификационного номера для пользователей, которые подключаются к Skype для бизнеса с помощью IP-телефонов.</span><span class="sxs-lookup"><span data-stu-id="532d7-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="532d7-106">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="532d7-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="532d7-107">Для создания политики ПИН-кодов на уровне пользователя или сайта выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="532d7-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="532d7-108">Создание политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="532d7-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="532d7-109">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="532d7-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="532d7-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532d7-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="532d7-111">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика в отношении ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="532d7-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="532d7-112">На странице **Политика в отношении ПИН-кодов** щелкните **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="532d7-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="532d7-p102">Чтобы создать политику на уровне пользователя, щелкните **Политика пользователя**. В окне **Новая политика в отношении ПИН-кодов**, в поле **Имя**, введите имя, описывающее политику.</span><span class="sxs-lookup"><span data-stu-id="532d7-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="532d7-p103">Чтобы создать политику на уровне сайта, выберите пункт **Политика сайта**. В поле поиска **Выбор сайта** введите имя (или часть имени) сайта, для которого требуется создать политику. В появившемся списке сайтов выберите нужный и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="532d7-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="532d7-118">В поле **Описание** введите описание политики в отношении ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="532d7-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="532d7-p104">В поле **Минимальная длина ПИН-кода** введите или выберите минимальную длину ПИН-кода, которую требуется разрешить. Минимальная длина по умолчанию составляет пять цифр.</span><span class="sxs-lookup"><span data-stu-id="532d7-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="532d7-p105">Чтобы иметь возможность задать максимальное число попыток входа перед блокированием пользователя, установите флажок **Задать максимальное число попыток входа**. Если этот параметр не выбран, максимальное число разрешенных попыток входа автоматически определяется в зависимости от длины ПИН-кода. По умолчанию максимальное число попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="532d7-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="532d7-124">Если установлен флажок **Задать максимальное число попыток входа**, в поле **Максимальное число попыток входа** введите или выберите максимальное число попыток входа, которое требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="532d7-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="532d7-p106">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Включить конечный срок действия ПИН-кодов**. Если этот параметр не выбран, ПИН-коды не будут иметь ограничений по сроку действия. По умолчанию ПИН-коды не имеют ограничений по сроку действия.</span><span class="sxs-lookup"><span data-stu-id="532d7-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="532d7-128">Если флажок **Разрешить окончание срока действия ПИН-кода** установлен, то в поле **Срок действия ПИН-кода истекает после (дней)** введите или выберите максимальное число дней, после которых ПИН-коды становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="532d7-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="532d7-p107">В поле **История значений ПИН-кода** введите число ПИН-кодов, которое пользователь должен создать перед тем, как он сможет использовать их повторно. По умолчанию пользователи могут повторно использовать ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="532d7-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="532d7-p108">Чтобы разрешить распространенные последовательности цифр в ПИН-кодах, такие как "1234" и "8888", установите флажок **Разрешить общие шаблоны**. Если не выбрать этот параметр, будут разрешены только сложные наборы цифр. По умолчанию разрешены только сложные наборы цифр.</span><span class="sxs-lookup"><span data-stu-id="532d7-p108">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="532d7-134">Мы рекомендуем не разрешать использование распространенных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="532d7-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="532d7-135">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="532d7-135">Click **Commit**.</span></span>
    

