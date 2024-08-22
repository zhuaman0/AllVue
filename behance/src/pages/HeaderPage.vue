<template>
	<q-layout view="hHh lpR fF">
	  <q-header reveal elevated bordered class="bg-white row">
		 <div class="main-header">
			<div class="header-part first-part">
			  <h1>TravelEase</h1>
			  <ul class="nav-items">
				 <li>Solutions</li>
				 <li>Pricing</li>
				 <li>Resources</li>
				 <li>Customers</li>
				 <li>Careers</li>
			  </ul>
			</div>
			<div class="header-part second-part">
			  <q-btn
				 class="custom-btn1"
				 color="primary"
				 label="Sign in"
				 @click="onClick"
				 rounded
			  />
			  <q-btn
				 class="custom-btn"
				 label="Sign up"
				 @click="onClick"
				 rounded
			  />
			</div>
			<q-btn
			  class="menu-btn"
			  icon="menu"
			  flat
			  round
			  dense
			  @click="toggleDrawer"
			/>
		 </div>
	  </q-header>

	  <q-drawer
		 v-model="drawerLeft"
		 side="left"
		 bordered
		 :width="300"
		 content-class="bg-grey-3"
	  >
		 <q-list>
			<ul class="drawer-nav-items">
			  <li>Solutions</li>
			  <li>Pricing</li>
			  <li>Resources</li>
			  <li>Customers</li>
			  <li>Careers</li>
			</ul>
		 </q-list>
	  </q-drawer>

	  <q-page-container>
		 <q-page class="q-pa-md">
		 </q-page>
	  </q-page-container>
	</q-layout>
 </template>

 <script setup>
 import { ref } from 'vue';

 const drawerLeft = ref(false);

 const toggleDrawer = () => {
	if (window.innerWidth <= 1070) {
	  drawerLeft.value = !drawerLeft.value;
	}
 };

 const onClick = () => {
	// Handle the click event for buttons
 };
 </script>

 <style scoped>
 * {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
 }

 .main-header {
	margin: 0 60px;
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 100%;
	height: 100%;
 }

 .header-part {
	display: flex;
	align-items: center;
 }

 .header-part h1 {
	color: black;
	font-size: 40px;
	font-weight: bold;
	margin-right: 20px;
 }

 .nav-items {
	display: flex;
	margin: 0;
	padding: 0;
	list-style: none;
 }

 .nav-items li {
	color: black;
	margin: 0 15px;
	font-size: 17px;
 }

 .drawer-nav-items {
	padding: 10px;
	list-style: none;
 }

 .drawer-nav-items li {
	color: black;
	margin: 10px 0;
	font-size: 17px;
 }

 .second-part {
	display: flex;
	align-items: center;
	gap: 20px;
 }

 .custom-btn,
 .custom-btn1 {
	padding: 0 20px;
 }

 .custom-btn {
	background-color: white;
	color: black;
 }

 .menu-btn {
	display: none;
	color: black;
	font-size: 20px;
 }

 @media (max-width: 1070px) {
	.nav-items,
	.second-part {
	  display: none;
	}

	.menu-btn {
	  display: flex;
	}
 }
 </style>
