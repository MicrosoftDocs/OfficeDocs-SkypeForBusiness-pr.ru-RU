---
title: Процесс развертывания для объявлений приложения в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Процесс развертывания и действия для объявлений приложения в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 6aabc5090d233b991e1fd89ef61f364a6b1c5666
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968915"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="7a626-103">Процесс развертывания для объявлений приложения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7a626-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="7a626-104">Процесс развертывания и действия для объявлений приложения в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7a626-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7a626-105">Объявление приложения — это функция корпоративной голосовой связи, которая позволяет настроить, что происходит с вызовы неназначенных extensions (расширения, которые являются допустимыми для вашей организации, но не назначенные человека или телефон).</span><span class="sxs-lookup"><span data-stu-id="7a626-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="7a626-106">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="7a626-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="7a626-107">Приложение оповещения устанавливается как компонент приложения группы ответа на сервере переднего плана или сервере Standard Edition, при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7a626-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7a626-108">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7a626-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="7a626-109">В этом разделе Обзор действий, необходимых для развертывания приложения объявлений.</span><span class="sxs-lookup"><span data-stu-id="7a626-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="7a626-110">Перед настройкой извещения, необходимо развернуть корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7a626-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="7a626-111">Компоненты, необходимые для объявлений приложения установлены и включены при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7a626-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="7a626-112">**Процесс развертывания объявлений**</span><span class="sxs-lookup"><span data-stu-id="7a626-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="7a626-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="7a626-113">**Phase**</span></span>|<span data-ttu-id="7a626-114">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="7a626-114">**Steps**</span></span>|<span data-ttu-id="7a626-115">**Роли **</span><span class="sxs-lookup"><span data-stu-id="7a626-115">**Roles**</span></span>|<span data-ttu-id="7a626-116">**Документация по развертыванию**</span><span class="sxs-lookup"><span data-stu-id="7a626-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a626-117">Настройка параметров объявлений</span><span class="sxs-lookup"><span data-stu-id="7a626-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="7a626-118">Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</span><span class="sxs-lookup"><span data-stu-id="7a626-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="7a626-119">Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="7a626-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="7a626-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a626-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="7a626-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a626-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="7a626-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a626-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="7a626-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a626-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="7a626-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a626-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="7a626-125">Создание и удаление оповещения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7a626-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="7a626-126">Создание или изменение диапазона неназначенных номеров в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7a626-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="7a626-127">Проверка развертывания объявления</span><span class="sxs-lookup"><span data-stu-id="7a626-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="7a626-128">Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</span><span class="sxs-lookup"><span data-stu-id="7a626-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="7a626-129">(Необязательно) Проверка развертывания объявлений в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7a626-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

