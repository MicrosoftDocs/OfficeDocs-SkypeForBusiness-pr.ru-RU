---
title: Проверка репликации раздела схемы
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Чтобы убедиться, что расширение схемы успешно реплицировано в лесу доменных служб Active Directory, сделайте следующее:'
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800549"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="36285-103">Проверка репликации раздела схемы</span><span class="sxs-lookup"><span data-stu-id="36285-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="36285-104">Чтобы убедиться, что расширение схемы успешно реплицировано в лесу доменных служб Active Directory, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="36285-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="36285-105">Войдите на контроллер домена (кроме контроллера домена, который содержит роль хозяина схемы) в лесу доменных служб Active Directory, где расширения схемы были применены в качестве члена группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="36285-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="36285-106">Откройте редактор ADSI: щелкните последовательно **Пуск**, **Администрирование** и **Редактирование ADSI**.</span><span class="sxs-lookup"><span data-stu-id="36285-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="36285-107">Можно также щелкнуть **Пуск**, а затем выбрать команду **Выполнить** и ввести **adsiedit.msc**, чтобы запустить редактор ADSI.</span><span class="sxs-lookup"><span data-stu-id="36285-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="36285-108">В дереве консоли управления (MMC) щелкните "Редактирование ADSI" (если еще не выбрано).</span><span class="sxs-lookup"><span data-stu-id="36285-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="36285-109">В меню **Действие** выберите **Подключение к**.</span><span class="sxs-lookup"><span data-stu-id="36285-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="36285-110">В диалоговом окне **Параметры подключения** в разделе **Выберите известный контекст именования** выберите **Схема** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36285-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="36285-p101">В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion. Если объект существует, атрибут **rangeUpper** имеет значение 1150, а атрибут **rangeLower** — значение 3, то схема была успешно обновлена и реплицирована. Если объекта не существует или значения атрибутов **rangeUpper** и **rangeLower** не указаны, то изменение или репликация схемы не выполнены.</span><span class="sxs-lookup"><span data-stu-id="36285-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="36285-114">Если проверка репликации схемы не показывает успешного выполнения репликации, подождите 15 минут и повторите проверку.</span><span class="sxs-lookup"><span data-stu-id="36285-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="36285-115">Репликация Active Directory основана на модели свободной согласованности, и некоторые задержки репликации могут возникать в зависимости от ряда факторов на сервере и в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="36285-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

