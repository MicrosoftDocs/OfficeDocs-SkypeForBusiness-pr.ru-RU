---
title: Настройка двухфакторной проверки подлинности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Сводка: Управление двухфакторной проверкой подлинности в Skype для бизнеса Server.'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297563"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="e4c5c-103">Настройка двухфакторной проверки подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e4c5c-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="e4c5c-104">**Сводка:** Управление двухфакторной проверкой подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="e4c5c-105">Двухфакторная проверка подлинности обеспечивает повышенную безопасность и требует от пользователей использования двух критериев проверки подлинности: сочетания пароля и имени пользователя и маркер или сертификата.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="e4c5c-106">Это также называется "что вам нужно, что вы знаете".</span><span class="sxs-lookup"><span data-stu-id="e4c5c-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="e4c5c-p102">Типичным примером двухфакторной проверки подлинности с помощью сертификата может послужить использование смарт-карт. Смарт-карта включает в себя сертификат, связанный с учетной записью пользователя, и проверяется с помощью информации о пользователе и сертификате, хранящейся на сервере. Сервер сравнивает информацию о пользователе (имя пользователя и пароль) с представленным сертификатом, в результате чего происходит проверка учетных данных и определяется подлинность пользователя.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="e4c5c-110">При настройке среды Skype для бизнеса Server для поддержки двухфакторной проверки подлинности имейте в виду следующие темы.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="e4c5c-111">Поддержка клиента</span><span class="sxs-lookup"><span data-stu-id="e4c5c-111">Client Support</span></span>

<span data-ttu-id="e4c5c-112">Накопительные обновления для Lync Server 2013: Июль 2013 для настольных компьютеров и клиент Skype для бизнеса — это единственные клиенты, которые в настоящее время поддерживают двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="e4c5c-113">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="e4c5c-113">Topology Requirements</span></span>

<span data-ttu-id="e4c5c-114">Пользователям настоятельно рекомендуется развертывать двухфакторную проверку подлинности с помощью специально выделенного сервера Skype для бизнеса (EDGE, режиссер и пулы пользователей).</span><span class="sxs-lookup"><span data-stu-id="e4c5c-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="e4c5c-115">Для включения пассивной проверки подлинности для пользователей Lync необходимо отключить другие способы проверки подлинности для других ролей и служб, включая:</span><span class="sxs-lookup"><span data-stu-id="e4c5c-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="e4c5c-116">**Тип конфигурации**</span><span class="sxs-lookup"><span data-stu-id="e4c5c-116">**Configuration Type**</span></span>|<span data-ttu-id="e4c5c-117">**Тип службы**</span><span class="sxs-lookup"><span data-stu-id="e4c5c-117">**Service Type**</span></span>|<span data-ttu-id="e4c5c-118">**Роль сервера**</span><span class="sxs-lookup"><span data-stu-id="e4c5c-118">**Server Role**</span></span>|<span data-ttu-id="e4c5c-119">**Тип проверки подлинности, который нужно отключить**</span><span class="sxs-lookup"><span data-stu-id="e4c5c-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4c5c-120">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="e4c5c-120">Web Service</span></span>  <br/> |<span data-ttu-id="e4c5c-121">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="e4c5c-121">WebServer</span></span>  <br/> |<span data-ttu-id="e4c5c-122">Директор</span><span class="sxs-lookup"><span data-stu-id="e4c5c-122">Director</span></span>  <br/> |<span data-ttu-id="e4c5c-123">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="e4c5c-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="e4c5c-124">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="e4c5c-124">Web Service</span></span>  <br/> |<span data-ttu-id="e4c5c-125">Веб-сервер</span><span class="sxs-lookup"><span data-stu-id="e4c5c-125">WebServer</span></span>  <br/> |<span data-ttu-id="e4c5c-126">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="e4c5c-126">Front End</span></span>  <br/> |<span data-ttu-id="e4c5c-127">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="e4c5c-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="e4c5c-128">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e4c5c-128">Proxy</span></span>  <br/> |<span data-ttu-id="e4c5c-129">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="e4c5c-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="e4c5c-130">Пограничный</span><span class="sxs-lookup"><span data-stu-id="e4c5c-130">Edge</span></span>  <br/> |<span data-ttu-id="e4c5c-131">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="e4c5c-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="e4c5c-132">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e4c5c-132">Proxy</span></span>  <br/> |<span data-ttu-id="e4c5c-133">Регистратор</span><span class="sxs-lookup"><span data-stu-id="e4c5c-133">Registrar</span></span>  <br/> |<span data-ttu-id="e4c5c-134">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="e4c5c-134">Front End</span></span>  <br/> |<span data-ttu-id="e4c5c-135">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="e4c5c-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="e4c5c-136">Пока эти типы проверки подлинности не будут отключены на уровне служб, все другие версии клиента не смогут выполнить успешный вход, поскольку в пределах вашего развертывания включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="e4c5c-137">Обнаружение служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e4c5c-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="e4c5c-138">DNS-записи, которые используются внутренними и внешними клиентами для поиска служб Skype для бизнеса, должны быть настроены для разрешения на сервер Skype для бизнеса, для которого не включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="e4c5c-139">В этой конфигурации пользователи из пулов Skype для бизнеса, для которых не включена двухфакторная проверка подлинности, не должны вводить PIN-код для проверки подлинности, а пользователи из пулов Skype для бизнеса, для которых включена Двухфакторная двухфакторная проверка подлинности, будут требуется для ввода ПИН-кода для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="e4c5c-140">Проверка подлинности Exchange</span><span class="sxs-lookup"><span data-stu-id="e4c5c-140">Exchange Authentication</span></span>

<span data-ttu-id="e4c5c-141">Пользователи, которые развернули двухфакторную проверку подлинности для Microsoft Exchange, могут обнаружить, что некоторые функции в клиенте недоступны.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="e4c5c-142">В настоящее время это дизайн, так как клиент Skype для бизнеса не поддерживает двухфакторную проверку подлинности для функций, которые зависят от интеграции Exchange.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="e4c5c-143">Контакты</span><span class="sxs-lookup"><span data-stu-id="e4c5c-143">Contacts</span></span>

<span data-ttu-id="e4c5c-144">Пользователи Skype для бизнеса, которые настроены на использование единой системы обмена контактными данными, смогут обнаружить, что их контакты больше не будут доступны после входа с помощью двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="e4c5c-145">Для удаления существующих контактов пользователей из единого хранилища контактов и их сохранения в Skype для бизнеса Server следует использовать командлет **Invoke-ксуксроллбакк** , прежде чем включить двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="e4c5c-146">Поиск по навыкам</span><span class="sxs-lookup"><span data-stu-id="e4c5c-146">Skill Search</span></span>

<span data-ttu-id="e4c5c-147">Пользователи, которые настроили функцию поиска по навыкам в среде Skype для бизнеса, смогут обнаружить, что эта функция не работает, если в Skype для бизнеса включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="e4c5c-148">Это объясняется тем, что Microsoft SharePoint не поддерживает двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="e4c5c-149">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="e4c5c-149">Credentials</span></span>

<span data-ttu-id="e4c5c-150">Существует ряд вопросов, связанных с развертыванием учетных данных Skype для бизнеса, которые могут повлиять на пользователей, которые настроены на использование двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="e4c5c-151">Удаление сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="e4c5c-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="e4c5c-152">Пользователи должны использовать параметр " **удалить мои данные для входа** " в клиенте Skype для бизнеса и удалять свою папку профиля SIP из%LocalAppData%\Microsoft\Office\15.0\Skype для бизнеса, прежде чем пытаться войти в первый раз с помощью двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="e4c5c-153">Отключение учетных данных NTC</span><span class="sxs-lookup"><span data-stu-id="e4c5c-153">DisableNTCredentials</span></span>

<span data-ttu-id="e4c5c-154">При использовании метода проверки подлинности Kerberos или NTLM для проверки подлинности автоматически используются учетные данные пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="e4c5c-155">В стандартном развертывании сервера Skype для бизнеса Server, где для проверки подлинности используется протокол Kerberos и (или) NTLM, пользователи не должны вводить свои учетные данные при каждом входе.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="e4c5c-156">Если у пользователя запрашиваются учетные данные перед появлением запроса ПИН-кода, на клиентском компьютере мог быть случайно настроен раздел реестра **DisableNTCredentials** (возможно, через групповую политику).</span><span class="sxs-lookup"><span data-stu-id="e4c5c-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="e4c5c-157">Чтобы не допустить дополнительных запросов на ввод учетных данных, создайте на локальной рабочей станции следующий параметр реестра или используйте административный шаблон Skype для бизнеса, который будет применяться ко всем пользователям для определенного пула с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="e4c5c-158">Сохранение пароля</span><span class="sxs-lookup"><span data-stu-id="e4c5c-158">SavePassword</span></span>

<span data-ttu-id="e4c5c-159">При первом входе пользователя в Skype для бизнеса ему будет предложено сохранить свой пароль.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="e4c5c-160">Если флажок установлен, этот параметр позволяет сертификату клиента пользователя храниться в хранилище личных сертификатов, а учетные данные пользователя Windows — в диспетчере учетных данных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="e4c5c-161">Настройка реестра **савепассворд** должна быть отключена, если в Skype для бизнеса включена поддержка двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="e4c5c-162">Чтобы запретить пользователям сохранять пароли, измените следующий параметр реестра на локальной рабочей станции или используйте административный шаблон Skype для бизнеса, чтобы применить ко всем пользователям для определенного пула с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="e4c5c-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="e4c5c-163">Повтор маркера AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="e4c5c-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="e4c5c-p110">AD FS 2.0 обеспечивает функцию обнаружения повтора маркера, которая позволяет обнаружить и отменить ряд запросов, использующих один маркер. Эта функция поддерживает целостность запросов проверки подлинности в пассивном профиле федерации веб-служб и профиле SAML WebSSO, не позволяя использовать один маркер несколько раз.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="e4c5c-166">Функция обнаружения повтора маркера необходима в особо опасных условиях, например в интерактивных терминалах.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="e4c5c-167">Дополнительные сведения об определении воспроизведении маркеров можно найти в разделе рекомендации [по обеспечению безопасного планирования и развертыванию AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="e4c5c-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="e4c5c-168">Доступ внешнего пользователя</span><span class="sxs-lookup"><span data-stu-id="e4c5c-168">External User Access</span></span>

<span data-ttu-id="e4c5c-169">Настройка прокси-сервера ADFS или обратного прокси-сервера для поддержки двухфакторной проверки подлинности Skype для бизнеса из внешних сетей не рассматривается в указанных ниже разделах.</span><span class="sxs-lookup"><span data-stu-id="e4c5c-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e4c5c-170">См. также</span><span class="sxs-lookup"><span data-stu-id="e4c5c-170">See also</span></span>

[<span data-ttu-id="e4c5c-171">Настройка двухфакторной проверки подлинности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e4c5c-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
