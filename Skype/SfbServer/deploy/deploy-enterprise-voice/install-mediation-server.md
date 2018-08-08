---
title: Для установки сервера-посредника в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Сводка: Узнайте, как установить файлы для сервера-посредника в Скайп для Business Server.'
ms.openlocfilehash: b3314e5443a7aa881fa849fd3e3b5b639f72664e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002483"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="76c94-103">Для установки сервера-посредника в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="76c94-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="76c94-104">**Сводка:** Узнайте, как установить файлы для сервера-посредника в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="76c94-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="76c94-105">Для успешного выполнения этой процедуры необходимо войти на сервер как минимум с учетной записью локального администратора и пользователя домена, которая является членом группы RTCUniversalReadOnlyAdmins или группы, имеющей более высокие привилегии.</span><span class="sxs-lookup"><span data-stu-id="76c94-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="76c94-106">Используйте действия, описанные в этом разделе, для запуска Скайп для Business Server мастер развертывания для установки файлов для сервера-посредника на компьютере, который вы добавили пула серверов-посредников после использования Topology Builder для определения и публикации пула.</span><span class="sxs-lookup"><span data-stu-id="76c94-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="76c94-107">При установке файлов сервера-посредника, также установить и назначить сертификат, необходимые для каждого компьютера в пуле сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="76c94-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="76c94-108">В этом разделе предполагается, что уже определенные и опубликован автономного пула серверов-посредников в вашей топологии, как описано в статье [Deploy сервера-посредника в построителе топологий в Скайп для Business Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="76c94-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="76c94-109">Установка файлов для автономного пула серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="76c94-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="76c94-110">На установочном носителе щелкните правой кнопкой мыши _ \<установочного носителя\> _ **\Setup\amd64\Setup.exe**и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="76c94-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="76c94-111">На странице **Папка установки** нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="76c94-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="76c94-p102">На странице **Лицензионное соглашение** нажмите кнопку **Принимаю**, а затем нажмите **ОК**. (Требуется для продолжения.)</span><span class="sxs-lookup"><span data-stu-id="76c94-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="76c94-114">На странице **Скайп для мастер развертывания Business Server** щелкните **Установка или обновление Скайп для бизнес-системе сервера**.</span><span class="sxs-lookup"><span data-stu-id="76c94-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="76c94-115">Рядом со строкой **Шаг 1. Установка локального хранилища конфигурации** нажмите кнопку **Выполнить** и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="76c94-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="76c94-116">На странице **Настройка локальной реплики центрального хранилища управления** примите значение параметра **Извлечь данные непосредственно из центрального хранилища управления** по умолчанию и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="76c94-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="76c94-117">На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="76c94-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="76c94-118">Рядом с элементом **Шаг 2: программа установки или удаления Скайп компонентов сервера Business**, выберите пункт **выполнить**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="76c94-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="76c94-119">На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="76c94-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="76c94-p103">Нажмите кнопку **Выполнить** рядом со строкой **Шаг 3. Запрос, установка и назначение сертификатов**. Следуйте инструкциям на экране, приняв значения по умолчанию. Для сервера-посредника требуется один сертификат, поэтому вы выполните **шаг 3** дважды: один раз, чтобы издать нужный сертификат, и второй раз, чтобы его назначить.</span><span class="sxs-lookup"><span data-stu-id="76c94-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="76c94-123">После выдачи и корректного назначения сертификата нажмите рядом со строкой **Шаг 4. Запуск служб** кнопку **Выполнить** и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="76c94-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="76c94-124">После успешного завершения **шага 4** перезапустите сервер и войдите на него как участник группы DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="76c94-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="76c94-125">На компьютере, где выполняется Скайп для панели управления Business Server проверка на странице **Топология** Скайп для панели управления Business Server, которая отображается состояние службы сервера-посредника как зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="76c94-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="76c94-126">Если красный значок отображается X, выберите сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="76c94-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="76c94-127">В меню **Действие** выберите команду **Запустить все службы**.</span><span class="sxs-lookup"><span data-stu-id="76c94-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="76c94-128">При добавлении нескольких компьютеров для пула серверов-посредников выполните действия, описанные в эту процедуру на всех компьютерах в пуле сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="76c94-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="76c94-129">Если необходимо установить файлы для сервера-посредника для других компьютерах, затем следуйте инструкциям в разделе [Настройка магистрали в Скайп для Business Server](configure-trunks.md) для настройки параметров подключения линии связи между этого пула сервера-посредника (или всех посредника Серверы на сайте) и его однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="76c94-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

