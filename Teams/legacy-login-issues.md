---
title: Проблемы с получением сообщений и звонков на старые системы в Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Устранение неполадок, связанных с получением сообщений и звонков в старых системах
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489168"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="757a2-103">Проблемы с получением сообщений и звонков в устаревших системах</span><span class="sxs-lookup"><span data-stu-id="757a2-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="757a2-104">Пользователи могут столкнуться с проблемами при получении сообщений или звонков, если они используют старые версии Teams или вошли в систему с другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="757a2-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="757a2-105">Устаревшие настройки ADU</span><span class="sxs-lookup"><span data-stu-id="757a2-105">Legacy ADU setups</span></span>

 <span data-ttu-id="757a2-106">Если пользователи выполнили вход на компьютере, подключенном к домену, и вы **не хотите, чтобы их имена предварительно добавлялись на экран входа в Teams**, администраторы могут настроить следующий раздел реестра Windows для отключения предварительного заполнения имени пользователя (UPN):</span><span class="sxs-lookup"><span data-stu-id="757a2-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="757a2-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="757a2-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="757a2-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="757a2-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="757a2-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="757a2-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="757a2-110">Пропуск или игнорирование предварительного добавления имен пользователей, оканчивающихся на ".local" или ".corp", включено по умолчанию, поэтому вам не нужно настраивать раздел реестра для их отключения.</span><span class="sxs-lookup"><span data-stu-id="757a2-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="757a2-111">Дополнительные сведения можно найти в разделе [Вход в Microsoft Teams с использованием современной проверки подлинности](sign-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="757a2-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="757a2-112">Отзыв маркеров Skype</span><span class="sxs-lookup"><span data-stu-id="757a2-112">Skype token revocation</span></span>

<span data-ttu-id="757a2-113">При изменении или сбросе пароля старые клиенты не смогут получать сообщения и звонки в течение часа.</span><span class="sxs-lookup"><span data-stu-id="757a2-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="757a2-114">Чтобы устранить эту проблему, перезапустите приложение или перейдите к новым клиентам.</span><span class="sxs-lookup"><span data-stu-id="757a2-114">To resolve this issue, either restart the app or move to newer clients.</span></span>
