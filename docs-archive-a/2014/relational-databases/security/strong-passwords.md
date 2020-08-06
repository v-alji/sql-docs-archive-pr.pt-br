---
title: Senhas fortes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679768"
---
# <a name="strong-passwords"></a><span data-ttu-id="29dac-102">Senhas fortes</span><span class="sxs-lookup"><span data-stu-id="29dac-102">Strong Passwords</span></span>
  <span data-ttu-id="29dac-103">As senhas podem ser o link mais fraco em uma implantação de segurança de servidor.</span><span class="sxs-lookup"><span data-stu-id="29dac-103">Passwords can be the weakest link in a server security deployment.</span></span> <span data-ttu-id="29dac-104">Você sempre deveria tomar muito cuidado ao selecionar uma senha.</span><span class="sxs-lookup"><span data-stu-id="29dac-104">You should always take great care when you select a password.</span></span> <span data-ttu-id="29dac-105">Uma senha segura tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="29dac-105">A strong password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="29dac-106">Tem pelo menos 8 caracteres de extensão.</span><span class="sxs-lookup"><span data-stu-id="29dac-106">Is at least 8 characters long.</span></span>  
  
-   <span data-ttu-id="29dac-107">Combina letras, números e símbolos.</span><span class="sxs-lookup"><span data-stu-id="29dac-107">Combines letters, numbers, and symbol characters within the password.</span></span>  
  
-   <span data-ttu-id="29dac-108">Não se encontra em um dicionário.</span><span class="sxs-lookup"><span data-stu-id="29dac-108">Is not found in a dictionary.</span></span>  
  
-   <span data-ttu-id="29dac-109">Não é o nome de um comando.</span><span class="sxs-lookup"><span data-stu-id="29dac-109">Is not the name of a command.</span></span>  
  
-   <span data-ttu-id="29dac-110">Não é o nome de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="29dac-110">Is not the name of a person.</span></span>  
  
-   <span data-ttu-id="29dac-111">Não é o nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="29dac-111">Is not the name of a user.</span></span>  
  
-   <span data-ttu-id="29dac-112">Não é o nome de um computador.</span><span class="sxs-lookup"><span data-stu-id="29dac-112">Is not the name of a computer.</span></span>  
  
-   <span data-ttu-id="29dac-113">É alterada com frequência.</span><span class="sxs-lookup"><span data-stu-id="29dac-113">Is changed regularly.</span></span>  
  
-   <span data-ttu-id="29dac-114">É significativamente diferente das senhas anteriores.</span><span class="sxs-lookup"><span data-stu-id="29dac-114">Is significantly different from previous passwords.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="29dac-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as senhas podem conter até 128 caracteres, incluindo, símbolos e dígitos.</span><span class="sxs-lookup"><span data-stu-id="29dac-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain up to 128 characters, including letters, symbols, and digits.</span></span> <span data-ttu-id="29dac-116">Como os logons, nomes de usuários, funções e senhas são frequentemente usados nas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , determinados símbolos devem ser colocados entre aspas (") ou chaves ([ ]).</span><span class="sxs-lookup"><span data-stu-id="29dac-116">Because logins, user names, roles, and passwords are frequently used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, certain symbols must be enclosed by double quotation marks (") or square brackets ([ ]).</span></span> <span data-ttu-id="29dac-117">Use esses delimitadores nas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] quando o logon, o usuário, a função ou a senha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="29dac-117">Use these delimiters in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, user, role, or password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="29dac-118">Contém ou começa com um caractere de espaço.</span><span class="sxs-lookup"><span data-stu-id="29dac-118">Contains or starts with a space character.</span></span>  
  
-   <span data-ttu-id="29dac-119">Começa com o caractere $ ou \@.</span><span class="sxs-lookup"><span data-stu-id="29dac-119">Starts with the $ or \@ character.</span></span>  
  
 <span data-ttu-id="29dac-120">Se usados em uma cadeia de conexão OLE DB ou ODBC, um logon ou senha não deve conter os seguintes caracteres: [] {}() , ; ?</span><span class="sxs-lookup"><span data-stu-id="29dac-120">If used in an OLE DB or ODBC connection string, a login or password must not contain the following characters: [] {}() , ; ?</span></span> <span data-ttu-id="29dac-121">\* !</span><span class="sxs-lookup"><span data-stu-id="29dac-121">\* !</span></span> <span data-ttu-id="29dac-122">\@.</span><span class="sxs-lookup"><span data-stu-id="29dac-122">\@.</span></span> <span data-ttu-id="29dac-123">Esses caracteres são usados para iniciar uma conexão ou valores de conexão separados.</span><span class="sxs-lookup"><span data-stu-id="29dac-123">These characters are used to either initialize a connection or separate connection values.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="29dac-124">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="29dac-124">Related Content</span></span>  
 [<span data-ttu-id="29dac-125">Política de senha</span><span class="sxs-lookup"><span data-stu-id="29dac-125">Password Policy</span></span>](password-policy.md)  
  
  
