// ==UserScript==
// @name         Get Discord Token
// @namespace    http://tampermonkey.net/
// @version      0.3
// @description  Allows you to retrieve your user token for reference.
// @author       F.O.C.I.#0001
// @match        https://discord.com/activ*
// @match        https://discord.com/channel*
// @grant        none
// @run-at       document-start
// ==/UserScript==

(function () {
   'use strict';

   // impliment localstorage behavior using cookie
   //---------------------------------------------
   if(!window.localStorage) {
      Object.defineProperty(window, "localStorage", new(function () {
         var aKeys = [],
            oStorage = {};
         Object.defineProperty(oStorage, "getItem", {
            value: function (sKey) {
               return this[sKey] ? this[sKey] : null;
            },
            writable: false,
