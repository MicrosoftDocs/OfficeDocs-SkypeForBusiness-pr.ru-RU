---
title: Проверка репликации раздела схемы
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы убедиться в том, что расширение схемы успешно реплицировано в лесу доменных служб Active Directory, выполните указанные ниже действия.
ms.openlocfilehash: 2d739bece89d43d5d3be289be55c90c2a63b49fe
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705344"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="73dcc-103">Проверка репликации раздела схемы</span><span class="sxs-lookup"><span data-stu-id="73dcc-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="73dcc-104">Чтобы убедиться в том, что расширение схемы успешно реплицировано в лесу доменных служб Active Directory, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="73dcc-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="73dcc-105">Войдите в систему на контроллере домена (кроме контроллера домена, который владеет ролью хозяина схемы) в лесу доменных служб Active Directory, где они были применены как участники группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="73dcc-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="73dcc-106">Откройте оснастку "Редактирование ADSI": нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — пункт **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="73dcc-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="73dcc-107">Кроме того, нажмите кнопку **Пуск**, а затем — **выполнить**, введите **ADSIEdit. msc** , чтобы запустить Редактирование ADSI.</span><span class="sxs-lookup"><span data-stu-id="73dcc-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="73dcc-108">В дереве консоли управления (MMC), если он еще не установлен, нажмите кнопку изменить в ADSI.</span><span class="sxs-lookup"><span data-stu-id="73dcc-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="73dcc-109">В меню **Действие** щелкните **Подключиться к**.</span><span class="sxs-lookup"><span data-stu-id="73dcc-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="73dcc-110">В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="73dcc-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="73dcc-111">В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="73dcc-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="73dcc-112">Если этот объект существует, а значение атрибута **ранжеуппер** — 1150, а значение атрибута **ранжеловер** — 3, схема была успешно обновлена и реплицирована.</span><span class="sxs-lookup"><span data-stu-id="73dcc-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="73dcc-113">Если этот объект не существует или значения атрибутов **ранжеуппер** и **ранжеловер** не заданы, схема не была изменена или не была реплицирована.</span><span class="sxs-lookup"><span data-stu-id="73dcc-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="73dcc-114">Если ваша проверка репликации схемы пока не будет успешно выполнена, подождите около 15 минут, а затем снова установите флажок.</span><span class="sxs-lookup"><span data-stu-id="73dcc-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="73dcc-115">Репликация службы каталогов Active Directory основана на недостаточной модели согласованности, и может возникнуть задержка в некоторых случаях на основе ряда факторов сервера и инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="73dcc-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

