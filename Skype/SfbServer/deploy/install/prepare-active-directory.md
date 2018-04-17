---
title: Подготовка Active Directory для Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Summary: Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Подготовка Active Directory для Skype для бизнеса Server 2015
 
**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server works closely with Active Directory. You must prepare the Active Directory domain to work with Skype for Business Server. Эта процедура выполняется с помощью мастера развертывания один раз для каждого домена. Так как при этом создаются группы и в домен вносятся необходимые изменения, повторение данного процесса не требуется. Шаги с 1 по 5 могут выполняться в произвольном порядке. Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме. Подготовка службы Active Directory выполняется в шагах 4–8. For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![обзорная схема](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Подготовка Active Directory

Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS). Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared. The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology. Every server must be joined to the domain so that Skype for Business Server can work properly. 
  
> [!IMPORTANT]
> Для каждого домена в развертывании процедура подготовки Active Directory выполняется только один раз. 
  
Посмотрите видеоруководство **Подготовка Active Directory**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Подготовка Active Directory в мастере развертывания

1. Выполните вход в качестве пользователя с учетными данными администратора схемы для домена Active Directory.
    
2. Open Skype for Business Server Deployment Wizard.
    
    > [!TIP]
    > If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step. For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Нажмите ссылку **Подготовить Active Directory**.
    
4. **Step 1: Prepare schema**
    
    а. Проверьте необходимые условия для шага 1. Для доступа к ним щелкните раскрывающийся список, который находится под названием шага 1.
    
    б. Нажмите **Выполнить** в шаге 1, чтобы запустить мастер подготовки схемы.
    
    в. Обратите внимание, что для каждого развертывания эта процедура выполняется только один раз; нажмите **Далее**.
    
    г. После завершения подготовки схемы можно просмотреть журнал, нажав кнопку **Просмотреть журнал**. 
    
    e. Нажмите **Готово**, чтобы закрыть мастер подготовки схемы и вернуться к процедуре подготовки Active Directory.
    
5. **Step 2: Verify replication of schema partition**
    
    а. Выполните вход на контроллер домена.
    
    б. Откройте **Редактирование ADSI** из раскрывающегося меню **Сервис** в **диспетчере серверов**.
    
    в. В меню **Действие** щелкните **Подключиться к**.
    
    г. В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.
    
    e. В контейнере схемы выполните поиск объекта **CN=ms-RTC-SIP-SchemaVersion**. Если этот объект существует, и атрибут **rangeUpper** имеет значение 1150, а атрибут **rangeLower** — значение 3, то схема была успешно обновлена и реплицирована. Если объект не существует или значения атрибутов **rangeUpper** и **rangeLower** не указаны, то изменение или репликация схемы не выполнены.
    
6. **Step 3: Prepare current forest**
    
    а. Проверьте необходимые условия для шага 3. Для доступа к ним щелкните раскрывающийся список, который находится под названием шага 3.
    
    б. Нажмите **Выполнить** в шаге 3, чтобы запустить мастер подготовки текущего леса.
    
    в. Обратите внимание, что эта процедура выполняется только один раз для каждого из развертываний; нажмите **Далее**.
    
    г. Укажите домен для создания в нем универсальных групп. Если сервер входит в домен, можно выбрать **локальный домен** и нажать **Далее**.
    
    e. После завершения подготовки схемы можно просмотреть журнал, нажав кнопку **Просмотреть журнал**. 
    
    f. Нажмите **Готово**, чтобы закрыть мастер подготовки текущего леса и вернуться к процедуре подготовки Active Directory.
    
    g. Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    h. Type the command Get-CsAdForest, and press **Enter**.
    
    i. If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.
    
     ![Проверка репликации леса.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Step 4: Verify replication of the global catalog**
    
    а. На контроллере домена (желательно в месте, удаленном от других контроллеров домена) в лесу, для которого выполнялась подготовка, откройте окно **Пользователи и компьютеры Active Directory**.
    
    б. В окне **Пользователи и компьютеры Active Directory** разверните имя домена своего леса или дочернего домена.
    
    в. Щелкните контейнер **Пользователи** на левой панели и выполните поиск универсальной группы **CsAdministrators** на правой панели. Если группа CsAdministrator (в числе прочих новых универсальных групп, названия которых начинаются с Cs) имеется, репликация Active Directory прошла успешно.
    
    г. Если группы отсутствуют, вы можете принудительно ускорить выполнение репликации или подождать 15 минут и затем обновить правую панель. Если группы появились, репликация завершена.
    
8. **Step 5: Prepare the current domain**
    
    а. Проверьте необходимые условия для шага 5.
    
    б. Нажмите **Выполнить** в шаге 5, чтобы запустить мастер подготовки текущего домена.
    
    в. Обратите внимание, что эта процедура выполняется только один раз для каждого домена в развертывании; нажмите **Далее**.
    
    г. После завершения подготовки домена можно просмотреть журнал, нажав кнопку **Просмотреть журнал**. 
    
    e. Нажмите **Готово**, чтобы закрыть мастер подготовки текущего домена и вернуться к процедуре подготовки Active Directory.
    
    These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start. В их число входят все типы объектов Active Directory, такие как пользователи, контактные объекты, административные группы или любые другие типы объектов. You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.
    
9. **Step 6: Verify replication in the domain**
    
    а. Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    б. Use the command Get-CsAdDomain to verify replication within the domain.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Если параметр Domain не указан, в качестве значения используется локальный домен. 
  
    Пример запуска команды для локального домена contoso.local:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > Параметр GlobalSettingsDomainController позволяет указать, где хранятся глобальные параметры. Если параметры хранятся в контейнере System (это обычная ситуация при обновлении развертываний, когда глобальные параметры не переносятся в контейнер Configuration), определите контроллер домена в корне леса AD DS. Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу. Если не указать этот параметр, командлет будет считать, что параметры хранятся в контейнере Configuration, и будет ссылаться на любой контроллер домена в Active Directory. 
  
    в. If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.
    
10. **Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**
    
    а. Войдите как участник группы администраторов домена или группы RTCUniversalServerAdmins.
    
    б. Откройте раздел **Пользователи и компьютеры Active Directory**, разверните домен, щелкните контейнер **Пользователи**, щелкните правой кнопкой мыши CsAdministrator и выберите **Свойства**.
    
    в. В окне **Свойства CSAdministrator** перейдите на вкладку **Участники**.
    
    г. На вкладке **Участники** нажмите кнопку **Добавить**. В окне **выбора пользователей, контактов, компьютеров, учетных записей служб или групп** найдите поле **Введите имена объектов для выбора**. Введите имена пользователей или групп для добавления к группе CSAdministrators. Нажмите кнопку **ОК**.
    
    e. На вкладке **Участники** проверьте наличие выбранных пользователей или групп. Нажмите кнопку **ОК**.
    
    > [!CAUTION]
    > The Skype for Business Server Control Panel is a role-based access control tool. Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available. Предусмотрены также другие роли, предназначенные для выполнения определенных функций. For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups. 
  
    > [!CAUTION]
    > To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment. 
  
11. Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.
    
12. Убедитесь в том, что в качестве подтверждения успешного завершения рядом с пунктом **подготовка Active Director** стоит зелена галочка, как показано на рисунке.
    
     ![Подготовка Active Directory выполнена.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

