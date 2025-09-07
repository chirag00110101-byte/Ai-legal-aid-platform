## User Story 2: Multi-Channel OTP Delivery

**User Story ID:** US-102  
**Epic:** User Authentication  
**Sprint:** 1  
**Priority:** Must Have  
**Story Points:** 3

**User Story:**
As a user, I want to choose to receive OTP via SMS, WhatsApp, or email so that I can use my preferred communication method and have alternatives if one method fails.

**Linked Requirements:** 
- REQ-001: OTP-based User Authentication via mobile, WhatsApp, email

**Tasks:**
- [ ] TASK-201: Integrate SMS service provider (Twilio, AWS SNS, or similar)
- [ ] TASK-202: Set up WhatsApp Business API integration
- [ ] TASK-203: Configure email delivery service (SMTP/SendGrid)
- [ ] TASK-204: Add delivery preference selection UI (radio buttons/dropdown)
- [ ] TASK-205: Implement fallback delivery mechanism for failed attempts
- [ ] TASK-206: Add delivery status tracking and user notification
- [ ] TASK-207: Configure rate limiting per delivery channel
- [ ] TASK-208: Add retry logic for failed deliveries

**Acceptance Criteria:**
- [ ] User can select preferred OTP delivery method during login
- [ ] OTP delivered within 30 seconds via chosen channel
- [ ] If primary delivery fails, system automatically tries fallback method
- [ ] User receives clear confirmation of OTP delivery method used
- [ ] Failed delivery attempts logged with error details
- [ ] Rate limiting prevents spam (max 5 OTP requests per hour per user)
- [ ] Each delivery channel shows appropriate formatting (SMS: plain text, Email: formatted, WhatsApp: business message)

**Technical Requirements:**
- [ ] API integrations with third-party messaging services
- [ ] Secure credential management for external services
- [ ] Delivery status webhook handling
- [ ] Database fields for user communication preferences
- [ ] Error handling and logging for all delivery channels

**Definition of Done:**
- [ ] Code reviewed and approved by team lead
- [ ] Unit tests written and passing (>90% coverage)
- [ ] Integration tests with all three delivery channels
- [ ] Manual testing completed on real devices/accounts
- [ ] Error scenarios tested (network failures, invalid numbers/emails)
- [ ] Security review completed (no credentials exposed)
- [ ] Documentation updated (configuration guide, troubleshooting)
- [ ] Performance testing (handles concurrent OTP requests)

**Dependencies:**
- US-101 (OTP generation logic must be completed first)
- Third-party service accounts configured (SMS, WhatsApp, Email)
- Infrastructure setup for external API calls

**Assumptions:**
- Users have access to at least one communication channel
- Third-party messaging services are reliable and available
- WhatsApp Business API approval obtained (if using WhatsApp)
- Email deliverability configured properly (DKIM, SPF records)

**Notes:**
- Consider adding user preference storage for future logins
- WhatsApp integration may require business verification
- Test with international phone numbers for SMS
- Ensure compliance with SMS/email marketing regulations

***

