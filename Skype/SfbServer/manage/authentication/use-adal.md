---
title: Использование средства Modern Authentication (ADAL) со Skype для бизнеса
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Использование средства Modern Authentication (ADAL) со Skype для бизнеса
 
This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
  
## <a name="whats-in-this-article"></a>В этой статье

[Что такое ADAL?](use-adal.md#BKMK_ADAL)
  
[Настройка ADAL в пуле и настройка ADFS в качестве сервера маркеров безопасности](use-adal.md#BKMK_Config)
  
[Другие варианты включения входа ADAL (например, в клиентских приложениях Office)](use-adal.md#BKMK_Options)
  
[Клиенты, на которых служба Modern Authentication или ADAL не поддерживается](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>Что такое ADAL?
<a name="BKMK_ADAL"> </a>

ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication. This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens. ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.
  
Служба современной проверки подлинности может использоваться для получения доступа к защищенным ресурсам широким спектром приложений, которые выступают в качестве клиентов. In Skype for Business Server 2015, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.
  
Для подключения с применением средства Modern Authentication (на основе ADAL и OAuth 2.0) характерны некоторые стандартные элементы.
  
- There is a client making a request for a resource, in this case, the client is Skype for Business.
    
- There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server 2015.
    
- There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource. (OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)
    
In Skype for Business Server 2015 Modern Authentication (ADAL) conversations, Skype for Business Server 2015 communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2). The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly. If you haven't configured ADFS to work with Skype for Business Server 2015 please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.
  
> [!NOTE]
> During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved. For example, if the environment is purely Skype for Business Server 2015. This statement may be subject to change. 
  
Для успешной настройки необходимо загрузить пакет PowerShell, содержащий файлы .ps1 с командами, которые используются в ADAL.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Настройка ADAL в пуле и настройка ADFS в качестве сервера маркеров безопасности
<a name="BKMK_Config"> </a>

In this process, you connect your installation of ADFS to a Skype for Business Server 2015 pool that is configured for ADAL.
  
1. Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server 2015 pool or Standard Edition server. (Schedule maintenance windows, as needed, to run Windows Update for the automatic installation.)
    
2. On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script. (This needs to be done per ADFS farm or independent ADFS server(s). It does not need to be done on ADFS Proxy or proxies).
    
3. Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server 2015 pool or Standard Edition server. This needs to be done for all the Skype for Business Pools.
    
4. В PowerShell на серверах ADFS выполните сценарий Setup-AdfsOAuthTrustForSfB. Для этого потребуется ввести правильные URL-адреса внутреннего и внешнего полного доменного имени веб-службы. Ниже приводится пример.
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server 2015 Relying Party Trust in ADFS.
    
    > [!IMPORTANT]
    > Невозможно использовать пассивную проверку подлинности для пула одновременно с ADAL. Чтобы использовать ADAL, сначала отключите пассивную проверку подлинности. For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management. Expand Trust Relationships \> Relying Party Trusts. Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add. 
  
5. Return to your Skype for Business Server 2015 Front End or Standard Edition server server. From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business. You only need to do this step once per Skype for Business Server 2015 deployment. Ниже приводится пример:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties. The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Still on your Skype for Business Server 2015 Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN. You only need to do this step once per Skype for Business Server 2015 deployment. This is an example:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. При появлении запроса введите учетные данные тестового пользователя. Убедитесь, что тест завершен успешно.
    
    > [!NOTE]
    > When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt. Если он разрешается внешне, будет отображаться подсказка **Вход**. Обычно рекомендуется выполнить действия, которые приведут к отображению подсказки **Безопасность Windows**. Обратите внимание, что это поведение изменяется, особенно при реализации проверки подлинности по формам форм (FBA).
  
Также помните, что если URL-адрес STS разрешается во внутреннем сервере ADFS, а в веб-браузерах включена встроенная проверка подлинности Windows, на компьютерах, на которых много разных пользователей входят в клиентские приложения, будут возникать ошибки проверки подлинности, если в веб-браузере не настроено явным образом предлагать пользователям вводить учетные данные в определенной зоне безопасности. В качестве примера можно представить киоск. Учетная запись, под которой выполнен вход в операционную систему, может отличаться от учетной записи пользователя, под которой выполнен вход в клиент Skype для бизнеса. В этом случае могут возникнуть описанные здесь ошибки.
    
You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet). В этом диалоговом окне нажмите кнопку "Другой" и прокрутите до конца списка в диалоговом окне "Параметры". Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'. Если у вас есть киоски, где пользователь, запускающий клиент Skype для бизнеса, отличается (имеет другую учетную запись) от пользователя, вошедшего в компьютер, можно для таких компьютеров в целях тестирования установить для этого параметра значение "ВКЛ." в групповой политике.
    
Наконец, может отображаться несколько подсказок, так как система безопасности собирает данные, необходимые для проверки подлинности или авторизации вашей учетной записи.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Другие варианты включения входа ADAL (например, в клиентских приложениях Office)
<a name="BKMK_Options"> </a>

Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.
  
> [!IMPORTANT]
> Need to know what to expect from Modern Authentication sign-ins from your client apps? Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets. In the case of Office 2013 client apps, you will need to change some registry keys on client machines.
  
- Connect to Exchange Online and run the following cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Настройте эти разделы реестра для каждого устройства и компьютера, на котором необходимо включить современную проверку подлинности. В крупных организациях необходимо использовать объекты групповой политики. For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.
    
||||
|:-----|:-----|:-----|
|Параметр реестра  <br/> |Тип  <br/> |Значение  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Once these keys are set, set your Office 2013 apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero. Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Клиенты, на которых служба Modern Authentication или ADAL не поддерживается
<a name="BKMK_Support"> </a>

Некоторые версии клиентов не поддерживают протокол OAuth. Проверьте вашу версию клиента Office в разделе "Установка и удаление программ" панели управления и сравните с приведенными ниже номерами (и диапазоном) версий:
  
- Office Client 15.0.[0000-4766].\*
    
- Office Client 16.0.[0000-4293].\*
    
- Клиент Office 16.0.6001.[0000–1032]
    
- Office Client 16.0.[6000-6224].\*
    

