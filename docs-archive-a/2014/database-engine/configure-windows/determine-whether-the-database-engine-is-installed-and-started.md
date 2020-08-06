---
title: Determinar se o Mecanismo de Banco de Dados está instalado e foi iniciado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, determining if installed
- verifying Database Engine installation
- viewing Database Engine installation
- installed Database Engine verification [SQL Server]
ms.assetid: babb02e4-3521-4b75-b5df-e09205594375
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0a912cf4a89f208543605cc84f480b63955214ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684893"
---
# <a name="determine-whether-the-database-engine-is-installed-and-started"></a><span data-ttu-id="f111f-102">Determinar se o Mecanismo de Banco de Dados está instalado e iniciado</span><span class="sxs-lookup"><span data-stu-id="f111f-102">Determine Whether the Database Engine Is Installed and Started</span></span>
  <span data-ttu-id="f111f-103">Uma instalação bem sucedida do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instala arquivos no sistema de arquivos, cria entradas no Registro e instala várias ferramentas.</span><span class="sxs-lookup"><span data-stu-id="f111f-103">A successful installation of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] installs files to the file system, creates entries in the registry, and installs several tools.</span></span> <span data-ttu-id="f111f-104">Este tópico descreve como determinar se o [!INCLUDE[ssDE](../../includes/ssde-md.md)] está instalado e iniciado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f111f-104">This topic describes how to determine whether the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed and started in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f111f-105">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f111f-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="how-to-view-and-start-the-database-engine-by-using-sql-server-configuration-manager"></a><span data-ttu-id="f111f-106">Como exibir e iniciar o Mecanismo de Banco de Dados usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f111f-106">How to view and start the Database Engine by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="f111f-107">Clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**, aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="f111f-107">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
     <span data-ttu-id="f111f-108">Se você não tiver essas entradas no menu **Iniciar** , significa que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não está instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f111f-108">If you do not have these entries on the **Start** menu, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not correctly installed.</span></span> <span data-ttu-id="f111f-109">Execute a Instalação para instalar o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f111f-109">Run Setup to install the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="f111f-110">No **SQL Server Configuration Manager**, no painel esquerdo, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f111f-110">In **SQL Server Configuration Manager**, on the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="f111f-111">O painel direito lista vários serviços relacionados ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f111f-111">The right pane lists several services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f111f-112">Se o [!INCLUDE[ssDE](../../includes/ssde-md.md)] estiver instalado, o serviço do [!INCLUDE[ssDE](../../includes/ssde-md.md)] estará listado como **SQL Server (MSSQLSERVER)** se for a instância padrão; ou como **SQL Server (** \<*instance_name*> **)** se o [!INCLUDE[ssDE](../../includes/ssde-md.md)] estiver instalado como uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="f111f-112">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is listed as **SQL Server (MSSQLSERVER)** if it is the default instance; or **SQL Server (**\<*instance_name*>**)**, if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed as a named instance.</span></span> <span data-ttu-id="f111f-113">A menos que o nome da instância seja alterado, o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é instalado como uma instância nomeada denominada **SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="f111f-113">Unless the instance name is changed, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as a named instance with the name **SQLEXPRESS**.</span></span> <span data-ttu-id="f111f-114">Um ícone de triângulo verde indica que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] está em execução.</span><span class="sxs-lookup"><span data-stu-id="f111f-114">A green triangle icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is running.</span></span> <span data-ttu-id="f111f-115">Um ícone de quadrado vermelho indica que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] está parado.</span><span class="sxs-lookup"><span data-stu-id="f111f-115">A red square icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is stopped.</span></span>  
  
3.  <span data-ttu-id="f111f-116">Para iniciar o [!INCLUDE[ssDE](../../includes/ssde-md.md)], no painel direito, clique com o botão direito do mouse em [!INCLUDE[ssDE](../../includes/ssde-md.md)]e clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f111f-116">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)], in the right pane, right-click the [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Start**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f111f-117">Durante a instalação, o usuário pode selecionar um local no qual instalar os arquivos de programa e os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f111f-117">During setup, the user can select a location in which to install the program files and the database files.</span></span> <span data-ttu-id="f111f-118">Se o usuário aceitar o local padrão, os arquivos serão instalados em [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] e em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL.*x*, em que *x* é um número.</span><span class="sxs-lookup"><span data-stu-id="f111f-118">If the user accepts the default location, the files are installed to [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] and C:\Program Files\Microsoft SQL Server\MSSQL.*x*, where *x* is a number.</span></span>  
  
  
