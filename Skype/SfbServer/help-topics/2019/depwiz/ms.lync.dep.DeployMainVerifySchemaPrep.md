---
title: Проверка репликации раздела схемы
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы убедиться в том, что расширение схемы успешность репликации в лесу доменных служб Active Directory, выполните следующие действия.
ms.openlocfilehash: dc621d82edc9133ce45b93e781799419e55efe38
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216083"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="892cd-103">Проверка репликации раздела схемы</span><span class="sxs-lookup"><span data-stu-id="892cd-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="892cd-104">Чтобы убедиться в том, что расширение схемы успешность репликации в лесу доменных служб Active Directory, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="892cd-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="892cd-105">Войдите на контроллер домена (не является контроллером домена, которому назначена роль хозяина схемы) в лесу доменных служб Active Directory, где были применены расширения схемы как член группы "Администраторы предприятия".</span><span class="sxs-lookup"><span data-stu-id="892cd-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="892cd-106">Откройте редактор ADSI: Нажмите кнопку **Пуск**, выберите пункт **Администрирование**и выберите **Редактирование ADSI**.</span><span class="sxs-lookup"><span data-stu-id="892cd-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="892cd-107">Кроме того нажмите кнопку **Пуск**, а затем нажмите кнопку **запустить**, ввести **adsiedit.msc** , чтобы запустить редактор ADSI.</span><span class="sxs-lookup"><span data-stu-id="892cd-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="892cd-108">В дереве консоли управления (MMC) если он не установлен, установите флажок ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="892cd-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="892cd-109">В меню **Действие** щелкните **Подключиться к**.</span><span class="sxs-lookup"><span data-stu-id="892cd-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="892cd-110">В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="892cd-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="892cd-111">В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="892cd-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="892cd-112">Если этот объект уже существует и значение атрибута **rangeUpper** 1150 и значение атрибута **rangeLower** равно 3, схема была успешно обновляются и репликации.</span><span class="sxs-lookup"><span data-stu-id="892cd-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="892cd-113">Если этот объект не существует, или если значения атрибутов **rangeUpper** и **rangeLower** не как указано, затем схемы не были изменены или не была реплицирована.</span><span class="sxs-lookup"><span data-stu-id="892cd-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="892cd-114">Если ваше проверка репликации схемы еще не показывать успешность репликации, подождите около 15 минут и попробуйте снова.</span><span class="sxs-lookup"><span data-stu-id="892cd-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="892cd-115">Репликация Active Directory на основе модели свободном согласованности и выполнением некоторые задержка репликации на основании ряд факторов, влияющих на сервере и инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="892cd-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

