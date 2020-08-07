---
title: Propriedades do SQL Server Agent (página Conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.connection.f1
ms.assetid: d6a677ff-60ad-47ba-a0cb-df4193b165e0
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec9ae575f1ced510d95256d6827435e5b6ad89d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582255"
---
# <a name="sql-server-agent-properties-connection-page"></a><span data-ttu-id="7f8b0-102">Propriedades do SQL Server Agent (página Conexão)</span><span class="sxs-lookup"><span data-stu-id="7f8b0-102">SQL Server Agent Properties (Connection Page)</span></span>
  <span data-ttu-id="7f8b0-103">Use esta página para exibir e modificar as configurações da conexão do serviço do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f8b0-103">Use this page to view and modify the settings for the connection from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f8b0-104">Opções</span><span class="sxs-lookup"><span data-stu-id="7f8b0-104">Options</span></span>  
 <span data-ttu-id="7f8b0-105">**Servidor de host local do alias**</span><span class="sxs-lookup"><span data-stu-id="7f8b0-105">**Alias local host server**</span></span>  
 <span data-ttu-id="7f8b0-106">Especifica o alias a ser usado para se conectar à instância local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f8b0-106">Specifies the alias to use to connect to the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f8b0-107">Se você não puder usar as opções de conexão padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, defina um alias para a instância e especifique o alias aqui.</span><span class="sxs-lookup"><span data-stu-id="7f8b0-107">If you cannot use the default connection options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, define an alias for the instance and specify the alias here.</span></span>  
  
 <span data-ttu-id="7f8b0-108">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="7f8b0-108">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="7f8b0-109">Define a autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows como o método de autenticação usado para conectar-se com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f8b0-109">Sets [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7f8b0-110">O Agent conecta-se como a conta com que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é executado.</span><span class="sxs-lookup"><span data-stu-id="7f8b0-110">Agent connects as the account that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service runs as.</span></span>  
  
 <span data-ttu-id="7f8b0-111">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="7f8b0-111">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="7f8b0-112">Define a autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como o método de autenticação usado para conectar-se com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f8b0-112">Sets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7f8b0-113">A autenticação é fornecida para fins de compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="7f8b0-113">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="7f8b0-114">Para maior segurança, use a autenticação do Windows, se possível.</span><span class="sxs-lookup"><span data-stu-id="7f8b0-114">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="7f8b0-115">**Logon**</span><span class="sxs-lookup"><span data-stu-id="7f8b0-115">**Login**</span></span>  
 <span data-ttu-id="7f8b0-116">Especifica o nome de logon a ser usado para conectar-se com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f8b0-116">Specifies the login name to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7f8b0-117">**Senha**</span><span class="sxs-lookup"><span data-stu-id="7f8b0-117">**Password**</span></span>  
 <span data-ttu-id="7f8b0-118">Especifica a senha a ser usada para conectar-se com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f8b0-118">Specifies the password to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
