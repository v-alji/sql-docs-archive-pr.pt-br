---
title: Referência de erros e eventos (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server Database Engine]
- Database Engine [SQL Server], errors
- events [SQL Server Database Engine]
ms.assetid: ea928535-6fd1-4738-a8ed-ffb602f3825e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e991accfd0e6fdd4fa25746499308455eff85ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682262"
---
# <a name="errors-and-events-reference-database-engine"></a><span data-ttu-id="b77b6-102">Referência de erros e eventos (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="b77b6-102">Errors and Events Reference (Database Engine)</span></span>

<span data-ttu-id="b77b6-103">Esta seção contém Mecanismo de Banco de Dados mensagens de erro selecionadas que precisam de mais explicações.</span><span class="sxs-lookup"><span data-stu-id="b77b6-103">This section contains selected Database Engine error messages that need further explanation.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b77b6-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b77b6-104">In This Section</span></span>  
 <span data-ttu-id="b77b6-105">[Eventos e erros do mecanismo de banco de dados](database-engine-events-and-errors.md) Descreve o formato de [!INCLUDE[ssDE](../../includes/ssde-md.md)] mensagens de erro e explica como exibir mensagens de erro e retornar mensagens de erro para aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b77b6-105">[Database Engine Events and Errors](database-engine-events-and-errors.md) Describes the format of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages and explains how to view error messages and return error messages to applications.</span></span>  
  
 <span data-ttu-id="b77b6-106">Fornece uma explicação das mensagens de erro do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , as possíveis causas e ações que podem ser realizadas para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="b77b6-106">Provides an explanation of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="b77b6-107">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="b77b6-107">External Resources</span></span>  
 <span data-ttu-id="b77b6-108">Se você não encontrou as informações que está procurando na documentação do produto ou na Web, é possível fazer uma pergunta na comunidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou solicitar suporte do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b77b6-108">If you have not found the information you are looking for in the product documentation or on the Web, you can either ask a question in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community or request help from [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="b77b6-109">A tabela a seguir contém links para esses recursos e os descreve.</span><span class="sxs-lookup"><span data-stu-id="b77b6-109">The following table links to and describes these resources.</span></span>  
  
|<span data-ttu-id="b77b6-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="b77b6-110">Resource</span></span>|<span data-ttu-id="b77b6-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="b77b6-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b77b6-112">SQL Server Community</span><span class="sxs-lookup"><span data-stu-id="b77b6-112">SQL Server Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42455)|<span data-ttu-id="b77b6-113">Esse site contém links para grupos de notícias e fóruns monitorados pela comunidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b77b6-113">This site has links to newsgroups and forums monitored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community.</span></span> <span data-ttu-id="b77b6-114">Também lista fontes de informações da comunidade, como blogs e sites da Web.</span><span class="sxs-lookup"><span data-stu-id="b77b6-114">It also lists community information sources, such as blogs and Web sites.</span></span> <span data-ttu-id="b77b6-115">A comunidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é muito útil ao responder perguntas, embora não haja nenhuma garantia para as respostas dadas.</span><span class="sxs-lookup"><span data-stu-id="b77b6-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community is very helpful in answering questions, although an answer cannot be guaranteed.</span></span>|  
|[<span data-ttu-id="b77b6-116">SQL Server Developer Center Community</span><span class="sxs-lookup"><span data-stu-id="b77b6-116">SQL Server Developer Center Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42456)|<span data-ttu-id="b77b6-117">Esse site enfoca grupos de notícias, fóruns e outros recursos de comunidade que são úteis a desenvolvedores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b77b6-117">This site focuses on the newsgroups, forums, and other community resources that are useful to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] developers.</span></span>|  
|[<span data-ttu-id="b77b6-118">Ajuda e Suporte da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b77b6-118">Microsoft Help and Support</span></span>](https://go.microsoft.com/fwlink/?linkid=16419)|<span data-ttu-id="b77b6-119">Você pode usar esse site da Web para abrir um caso com um profissional de suporte do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b77b6-119">You can use this Web site to open a case with a [!INCLUDE[msCoName](../../includes/msconame-md.md)] support professional.</span></span>|  
  
  
