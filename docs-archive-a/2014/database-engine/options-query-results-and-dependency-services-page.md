---
title: Opções (página resultados da consulta e serviços de dependência) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.DependencyServicesGeneral
ms.assetid: dd7f6c31-7d7f-4972-854a-1419a2826dca
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 356714ee933fb40eda7038f4088309b6187f3ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582123"
---
# <a name="options-query-results-and-dependency-services-page"></a><span data-ttu-id="d4bc5-102">Opções (página Resultados da consulta e Serviços de Dependência)</span><span class="sxs-lookup"><span data-stu-id="d4bc5-102">Options (Query Results and Dependency Services Page)</span></span>
  <span data-ttu-id="d4bc5-103">Use esta página para especificar o servidor a ser conectado para Serviços de Dependência.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-103">Use this page to specify the server to connect for Dependency Services.</span></span> <span data-ttu-id="d4bc5-104">Os Serviços de Dependência permitem extrair informações sobre dependências entre objetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] armazenados em diferentes servidores.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-104">Dependency Services enables you to extract information about dependencies between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects stored on different servers.</span></span> <span data-ttu-id="d4bc5-105">Você exibe dependências de objeto usando a caixa de diálogo **dependências de objeto** no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4bc5-105">You view object dependencies by using the **Object Dependencies** dialog box in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="d4bc5-106">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="d4bc5-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="d4bc5-107">Abrir a caixa de diálogo de opções (página de resultados da consulta/Serviços de Dependência)</span><span class="sxs-lookup"><span data-stu-id="d4bc5-107">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="d4bc5-108">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="d4bc5-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-options-query-resultsdependency-services-page-dialog-box"></a><a name="open_dialog"></a><span data-ttu-id="d4bc5-109">Abrir a caixa de diálogo Opções (página resultados da consulta/serviços de dependência)</span><span class="sxs-lookup"><span data-stu-id="d4bc5-109">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>  
  
1.  <span data-ttu-id="d4bc5-110">No [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , clique em **Opções** no menu **ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="d4bc5-110">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="d4bc5-111">Expanda **Resultados da Consulta** e clique em **Serviços de Dependência**.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-111">Expand **Query Results**, and then click **Dependency Services**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="d4bc5-112">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="d4bc5-112">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="d4bc5-113">Opções</span><span class="sxs-lookup"><span data-stu-id="d4bc5-113">Options</span></span>  
 <span data-ttu-id="d4bc5-114">**Servidor dos Serviços de Dependência**</span><span class="sxs-lookup"><span data-stu-id="d4bc5-114">**Dependency Services server**</span></span>  
 <span data-ttu-id="d4bc5-115">Especifique o servidor em que os Serviços de Dependência estão instalados.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-115">Specify the server that Dependency Services is installed on.</span></span>  
  
 <span data-ttu-id="d4bc5-116">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="d4bc5-116">**Authentication**</span></span>  
 <span data-ttu-id="d4bc5-117">Selecione a Autenticação do Windows para fazer logon usando uma conta de usuário do Microsoft Windows ou selecione Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-117">Select Windows Authentication to log on using a Microsoft Windows user account, or select SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d4bc5-118">Quando um usuário se conecta com um nome de logon e senha especificados em uma conexão não confiável, o SQL Server efetua a autenticação verificando se uma conta de logon do SQL Server foi configurada e se a senha especificada corresponde à registrada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-118">When a user connects with a specified login name and password from a non-trusted connection, SQL Server performs the authentication by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="d4bc5-119">Se o SQL Server não localizar a conta de logon, ocorrerá uma falha na autenticação e o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-119">If SQL Server cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="d4bc5-120">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="d4bc5-120">**User name**</span></span>  
 <span data-ttu-id="d4bc5-121">Se você estiver usando a Autenticação do SQL Server, forneça um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-121">If using SQL Server Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="d4bc5-122">**Senha**</span><span class="sxs-lookup"><span data-stu-id="d4bc5-122">**Password**</span></span>  
 <span data-ttu-id="d4bc5-123">Se você estiver usando a Autenticação do SQL Server, forneça uma senha.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-123">If using SQL Server Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="d4bc5-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="d4bc5-124">**Test**</span></span>  
 <span data-ttu-id="d4bc5-125">Clique para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d4bc5-125">Click to test the connection.</span></span>