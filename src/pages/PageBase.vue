<template>
    <slot name="header"></slot>
    <div width="20%"><slot name="leftBody"></slot></div>
    <div width="60%"><slot name="content"></slot></div>
    <div width="20%"><slot name="rightBody"></slot></div>
    <div><slot name="footer"></slot></div>
</template>