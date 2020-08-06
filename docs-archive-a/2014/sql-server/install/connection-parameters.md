---
title: Parâmetros de conexão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], connections
- authentication [Upgrade Advisor]
- SQL Server Upgrade Advisor, connections
- connections [Upgrade Advisor]
- server instances [Upgrade Advisor]
- default server instances
- analyzing system [Upgrade Advisor], connections
ms.assetid: f754d038-637a-4d8e-85b0-b242e6499d26
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27eb69dfd2c41710a47861e0992486267f692a3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571787"
---
# <a name="connection-parameters"></a><span data-ttu-id="a3ae5-102">Parâmetros de conexão</span><span class="sxs-lookup"><span data-stu-id="a3ae5-102">Connection Parameters</span></span>
  <span data-ttu-id="a3ae5-103">Para analisar certos tipos de servidor, como o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], você deve selecionar uma instância específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3ae5-103">To analyze certain server types, such as the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you must select a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a3ae5-104">A instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-104">The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is automatically selected.</span></span> <span data-ttu-id="a3ae5-105">Você pode alterar essa seleção, mas pode selecionar somente uma instância de cada vez para análise pelo Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-105">You can change this selection, but you can select only one instance at a time for analysis by Upgrade Advisor.</span></span> <span data-ttu-id="a3ae5-106">Se você incluiu um tipo de servidor que requer autenticação, deve indicar o modo de autenticação e as credenciais.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-106">If you have included a server type that requires authentication, you must enter the authentication mode and credentials.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3ae5-107">Opções</span><span class="sxs-lookup"><span data-stu-id="a3ae5-107">Options</span></span>  
 <span data-ttu-id="a3ae5-108">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="a3ae5-108">**Server name**</span></span>  
 <span data-ttu-id="a3ae5-109">Pré-populado com o nome do computador digitado no painel Componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3ae5-109">Pre-populated with the computer name that you entered in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components pane.</span></span>  
  
 <span data-ttu-id="a3ae5-110">**Nome da instância**</span><span class="sxs-lookup"><span data-stu-id="a3ae5-110">**Instance name**</span></span>  
 <span data-ttu-id="a3ae5-111">Selecione uma das instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponíveis no computador.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-111">Select from the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are available on the computer.</span></span> <span data-ttu-id="a3ae5-112">Se você não vir uma lista de instâncias, use MSSQLSERVER para verificar a instância padrão.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-112">If you do not see a list of instances, use MSSQLSERVER to scan the default instance.</span></span> <span data-ttu-id="a3ae5-113">Isso é especialmente relevante para computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-113">This is especially relevant for remote computers.</span></span> <span data-ttu-id="a3ae5-114">Você também pode usar a palavra ‘default’ para verificar a instância padrão.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-114">You can also use the word "default" to scan the default instance.</span></span>  
  
 <span data-ttu-id="a3ae5-115">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="a3ae5-115">**Authentication**</span></span>  
 <span data-ttu-id="a3ae5-116">Selecione um método na lista de modos de autenticação disponíveis neste computador.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-116">Select from the list of available authentication modes on this computer.</span></span> <span data-ttu-id="a3ae5-117">Por padrão, o modo de autenticação é a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-117">By default, the authentication mode is Windows Authentication.</span></span>  
  
 <span data-ttu-id="a3ae5-118">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="a3ae5-118">**User name**</span></span>  
 <span data-ttu-id="a3ae5-119">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], digite o nome de usuário na caixa.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-119">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, enter a user name in the box.</span></span> <span data-ttu-id="a3ae5-120">Recomendamos que o nome de usuário tenha credenciais administrativas neste computador.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-120">We recommend that the user name have administrative credentials on the computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3ae5-121">Se você selecionar Autenticação do Windows, o nome de usuário do usuário conectado no momento será preenchido na caixa de texto **nome de usuário** .</span><span class="sxs-lookup"><span data-stu-id="a3ae5-121">If you select Windows Authentication, the user name of the currently logged-on user is populated in the **User name** text box.</span></span>  
  
 <span data-ttu-id="a3ae5-122">**Senha**</span><span class="sxs-lookup"><span data-stu-id="a3ae5-122">**Password**</span></span>  
 <span data-ttu-id="a3ae5-123">Digite a senha para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="a3ae5-123">Enter the password for the specified user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ae5-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a3ae5-124">See Also</span></span>  
 <span data-ttu-id="a3ae5-125">[Trabalhando com o supervisor de atualização](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="a3ae5-125">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="a3ae5-126">Referência da interface de usuário do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="a3ae5-126">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
