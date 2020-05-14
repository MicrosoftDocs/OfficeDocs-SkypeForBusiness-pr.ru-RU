---
title: Планирование современной проверки подлинности в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Разделы, посвященные планированию проверки подлинности и авторизации для Skype для бизнеса Server, включая интеграцию с другими продуктами
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221583"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="b2c7f-103">Обсуждение проверки подлинности и авторизации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b2c7f-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="b2c7f-104">Проверка подлинности и авторизация связаны с основными понятиями, но для вас не требуется никаких действий (хотя и то, и другое).</span><span class="sxs-lookup"><span data-stu-id="b2c7f-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="b2c7f-105">Говоря простыми терминами, аусенЦиатион (определения) зависит только от конфиденциальных сведений, которые знают или имеют действительный пользователь, а также могут быть паролями, кодом, отпечатком пальцев, сертификатом, сочетанием утверждений пользователя или сочетанием этих вещей, которые используются совместно.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="b2c7f-106">Определения — это процесс подтверждения того, кто вы скажете.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="b2c7f-107">Авторизация (AuthZ) связана с тем, к чему у вас есть доступ, после того, как вы проверены.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="b2c7f-108">Она определяет, что вы можете просматривать, редактировать и иным способом получать доступ.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="b2c7f-109">Например, администратор семейства веб-сайтов может получить доступ к SharePoint Online, но если вы переключились на другую рабочую нагрузку, например Skype для бизнеса Online, у вас могут быть права на устранение неполадок пользователей, но не изменять конфигурацию сервера или серверов.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="b2c7f-110">В третьей рабочей нагрузке, например Exchange Online, может быть только средний доступ пользователя.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="b2c7f-111">Авторизация проверяет, что и сколько необходимо для служб/ворлоадс, приложений, файлов и других данных.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="b2c7f-112">В нашем примере используются Интернет-свойства, такие как SharePoint и Exchange Online, но процессы определения и AuthZ работают локально и в гибридной гибридной среде.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="b2c7f-113">В конечном итоге, такие инструменты, как AAD Connect и ADFS, участвуют в определения и AuthZ, синхронизируя локальные учетные записи и пароли в AD-AD (то есть Azure AD) или проходят в потоке AuthZ, чтобы пользователю не было часто запрашивать свои учетные данные, скажем, при переключении между рабочими нагрузками в облаке и созданием сценариев единого входа.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="b2c7f-114">Но они не сами несут ответственность за определения или AuthZ, а только часть механики.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="b2c7f-115">В настоящее время многие технологии считают, что эти процессы (определения и AuthZ) являются одним механизмом, и вы услышите множество ссылок на процесс проверки подлинности, который также включает в себя авторизацию.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="b2c7f-116">Важно помнить о том, что первый шаг в доступе пользователей — определения, проверим, кто вы говорят, и что авторизация использует знание того, кто должен иметь к нему доступ (как вы увидите с открытой авторизацией или OAuth).</span><span class="sxs-lookup"><span data-stu-id="b2c7f-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="b2c7f-117">Разделы по планированию проверки подлинности и авторизации</span><span class="sxs-lookup"><span data-stu-id="b2c7f-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="b2c7f-118">Использование современной проверки подлинности (ADAL) со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b2c7f-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="b2c7f-119">Топологии Skype для бизнеса, поддерживаемые современной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="b2c7f-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="b2c7f-120">Планирование отключения устаревших методов проверки подлинности от внутренней системы к сети.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

